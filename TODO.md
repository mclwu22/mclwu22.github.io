# Remaining items

Everything below is optional — the site is publishable as it stands.

## 1. Result figure  (biggest remaining visual upgrade)
Export one BrainDINO figure to `figures/braindino.png`, then uncomment the
`<figure>` block in the BrainDINO project section of index.html.
Candidates already on disk, under
`~/Desktop/Med_DINOv3/Foundation_model_paper_contents/FINAL_result_overview/`:
  - brats_backbone_dice_plot_transposed_with_std.png
  - combined_figure_agebin_pvalues_adjusted.png
The label-ratio curve (gap widening as labels get scarcer) is the most legible
single result for a non-specialist reader.

## 2. LinkedIn
index.html has one `href="#"` left, on the LinkedIn button. Either fill it in
or delete that one `<a>` line.

## 3. Fix your CV, not the site
- The Google Scholar link in `Yizhou_Wu_CV.pdf` is broken: the LaTeX placeholder
  was never replaced, so it points at
  `https://scholar.google.com/citations?user=Google Scholar`.
  Correct target: https://scholar.google.com/citations?user=cyNeIz0AAAAJ&hl=en
- The CV lists BrainDINO as "manuscript in preparation". It is now a public
  preprint (arXiv:2604.27277) with public code. Update that line.

## Done
- Photo, CV PDF, Google Scholar link, publications (6, matching Scholar),
  GE Healthcare experience, education, service, teaching, skills.
- Draft banner removed.
- Job-specific framing removed — no "why this transfers to X" callouts.
