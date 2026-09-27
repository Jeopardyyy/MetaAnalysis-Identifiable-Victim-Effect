# Re-analysis of the Identifiable Victim Effect

A re-analysis of Lee & Feeley (2016), *"The identifiable victim effect: a meta-analytic review"* (Social Influence, 11(3), 199–215), completed as a research assistant selection task for Prof. Max Maier at Warwick Business School.

## Background

Lee and Feeley (2016) meta-analysed 41 study-level comparisons of helping identified vs. unidentified ("statistical") victims and reported a small, just-significant overall effect (r ≈ .05). Small effects from small, heterogeneous literatures can be sensitive to publication bias, so this project re-extracts their study-level data and re-examines the result under a different estimator, plus two publication-bias diagnostics.

## What this does

1. Re-extracts the 41 study-level effect sizes from the paper's Table 1
2. Converts correlations to Fisher's z and re-runs a random-effects meta-analysis using REML (vs. the original paper's DerSimonian-Laird estimator)
3. Assesses publication bias via **Egger's regression test** and the **trim-and-fill** procedure
4. Compares corrected vs. original pooled estimates, with a forest plot

## Key findings

- REML re-analysis produced an almost identical point estimate to the original (r = .053 vs. r = .05), but a p-value that narrowly missed conventional significance (p = .078 vs. p = .038) - the same 41 effect sizes, different variance estimator, different significance conclusion.
- Neither Egger's test nor trim-and-fill found evidence of publication bias; trim-and-fill estimated zero missing studies.
- Substantial heterogeneity across studies (I² ≈ 74.7%), so the "no missing studies" result is read here as "no detectable small-study effect" rather than proof publication bias is absent.

Full discussion, limitations, and references are in the report itself.

## Repository contents

| File | Description |
|---|---|
| `Analysis.Rmd` | R Markdown source - full code, commentary, and write-up |
| `Analysis.html` | Knitted report (open in a browser, or view via [htmlpreview](https://htmlpreview.github.io/)) |
| `table1.csv` | Study-level effect sizes (r, N) extracted from the paper's Table 1 |

The original paper is not included here for copyright reasons - see [DOI: 10.1080/15534510.2016.1216891](https://doi.org/10.1080/15534510.2016.1216891).

## Reproducing this

```r
install.packages(c("tidyverse", "metafor", "readr", "knitr"))
rmarkdown::render("Analysis.Rmd")
```

Seed is set (`set.seed(20)`) for full reproducibility. Package versions used are listed via `sessionInfo()` at the end of the report.

## Limitations

- Only two publication-bias methods were implemented within the task's time constraints (PET-PEESE or selection models could add further insight)
- With only 41 studies, bias-detection methods have limited power - results are suggestive, not conclusive
- Some studies share authors/samples (e.g. multiple Kogut & Ritov experiments); dependency between these is not modelled
- No moderator analyses were conducted despite substantial heterogeneity

## References

Full reference list is in `Analysis.Rmd` / `Analysis.html`.
