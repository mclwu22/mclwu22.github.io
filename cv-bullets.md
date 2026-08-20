# CV bullets — Generative Sequential Recommendation on Amazon Reviews 2023

Audience: recommendation / LLM research internship.
Every number below is verbatim from the project record. Stage 2 is written as
*designed* because it has not been trained — no Recall@K / NDCG@K numbers exist yet.

---

## Concise version (4 bullets)

- **Engineered** a single-node PySpark pipeline over **59.77M** Amazon reviews into an
  18.04M/2.39M/2.39M leave-one-out benchmark; explicit schemas cut the working set **26GB → 3.6GB**.

- **Cut** iterative k-core filtering from a killed job (round 7, >250s) to **8 rounds in 237s** by
  caching the lazy DAG — a **15×** per-round speedup.

- **Trained** an RQ-VAE (3 residual codebooks × 256, straight-through estimator, k-means init,
  dead-code revival) over **715,729** frozen Sentence-T5 embeddings, reaching **100% codebook
  utilization** at all three levels with no collapse.

- **Quantified** skew rather than assuming it: a **1160×** hot-item ratio yielded only **1.05×/1.18×**
  partition imbalance; pre-filtering metadata 3.5M → 715k rows enabled a broadcast join **1.37×**
  faster than sort-merge.

---

## Detailed version (4 bullets)

- **Engineered** a single-node PySpark pipeline (32 cores / 251GB RAM) over Amazon Reviews 2023:
  deduplicated **59.77M → 59.14M** reviews, cut the working set **26GB → 3.6GB** with explicit schemas,
  and applied iterative 5-core filtering (22M → 2.39M users; 3.5M → 715k items; 2.69 → 9.55
  interactions/user) to build an **18.04M/2.39M/2.39M** leave-one-out benchmark.

- **Diagnosed** lazy-DAG recomputation in iterative k-core filtering: uncached, round 6 alone took
  **188s** (**15×** a cached round) and round 7 was killed past 250s; adding `.cache()` converged all
  **8 rounds in 237s**.

- **Quantified** skew instead of assuming it — a **1160×** hot-item ratio (13,970 vs. median 12)
  produced only **1.05×/1.18×** row imbalance across 256 partitions — and converted a failed 3.5M-row
  broadcast (>1GB, over driver `maxResultSize`) into a **BroadcastHashJoin 1.37× faster** than
  SortMergeJoin by pre-filtering to 715k items, verified via `.explain()`; reported AQE as a null
  result (7.0s vs. 8.2s).

- **Trained** an RQ-VAE (768→32 encoder; 3 residual codebooks × 256; straight-through estimator,
  k-means init, dead-code revival) over **715,729** frozen Sentence-T5 embeddings, cutting
  reconstruction loss **0.67 → 0.42** at **100% codebook utilization** across all three levels, and
  **designed** the T5 encoder–decoder generative-retrieval stage with constrained beam search over the
  resulting Semantic ID space.

---

## If you want Stage 2 stated as complete

Only one clause needs changing — the tail of the last detailed bullet:

> ...and **designed** the T5 encoder–decoder generative-retrieval stage with constrained beam search
> over the resulting Semantic ID space.

Any stronger verb ("trained", "built", "evaluated") invites the follow-up question
*"what Recall@K did you get?"*, which currently has no answer. Train Stage 2 first,
then this bullet upgrades itself with real numbers.
