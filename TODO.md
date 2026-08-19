# Fill these in before you send the link

Ordered by how much they matter to a recruiter.

## 1. Resume PDF  (highest impact — most recruiters click this first)
Drop your resume in this folder named exactly `Yizhou_Wu_Resume.pdf`.
The JD says: **state your availability (start date, end date) clearly in your resume.**

## 2. Links  (search index.html for `TODO`)
- [ ] GitHub — I guessed `github.com/mclwu22` from your git config. Confirm or fix.
- [ ] Google Scholar — replace `href="#"` (2 places: hero + contact)
- [ ] LinkedIn — replace `href="#"` (2 places: hero + contact)

## 3. Photo  — DONE
`photo.jpg` is in place (512x512, cropped from your headshot) and wired into index.html.

## 4. One figure  (this is the single biggest visual upgrade)
Export a BrainDINO result figure to `figures/braindino.png` and uncomment the
`<figure>` block in the BrainDINO project. Good candidates already on disk:
  ~/Desktop/Med_DINOv3/Foundation_model_paper_contents/FINAL_result_overview/
    - brats_backbone_dice_plot_transposed_with_std.png
    - combined_figure_agebin_pvalues_adjusted.png
A label-ratio curve showing the gap widening under label scarcity is the most
persuasive one for this JD.

## 5. Facts I could not verify — check these yourself
- [ ] **Slice count.** Your two abstract drafts disagree: one says 7.2M, the newer
      one says ~6.6M. I used **6.6M**. Make the site match whatever you submit.
- [ ] **Publications.** I only found the BrainDINO manuscript. Add every other paper,
      workshop paper, and preprint — co-authored ones count.
- [ ] **Skills list.** I inferred SQL and Bash. Delete anything you don't want to be
      interviewed on. Note the JD asks for Spark/Hadoop/MapReduce — I did NOT add
      those since I saw no evidence. If you have used them, add them; if not, leave
      them off and don't bluff.
- [ ] **PhD year / expected graduation.** Not stated on the site yet. Consider adding
      "PhD Candidate (expected 20XX)" to the hero.

## 6. Delete the draft banner
Remove the `<div class="draft">…</div>` block near the top of index.html
(it's marked with comments). Do this LAST, as your final check.
