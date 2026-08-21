# ProbBreed Presentation

A journal club presentation on **[ProbBreed](https://github.com/saulo-chaves/ProbBreed)** — an R package for calculating the risk of cultivar recommendation in multi-environment trials — prepared for the Quantitative Genetics and Statistical Learning Lab (UFV).

## 🔗 Live links

| | |
|---|---|
| 📊 **Slide deck** (theory & concepts) | **[Open presentation](https://barbosawf.github.io/ProbBreed_Presentation/presentation_probbreed.html)** |
| 💻 **Hands-on tutorial** (fitting `bayes_met()` on real data) | **[Open tutorial](https://barbosawf.github.io/ProbBreed_Presentation/hands_on_tutorial.html)** |
| 🏠 Landing page with both links | **[barbosawf.github.io/ProbBreed_Presentation](https://barbosawf.github.io/ProbBreed_Presentation/)** |

## Contents

| File | Description |
|---|---|
| [`presentation_probbreed.qmd`](presentation_probbreed.qmd) | Slide deck source (revealjs) — theory, Bayesian model priors, and the probability formulas behind the package |
| [`hands_on_tutorial.qmd`](hands_on_tutorial.qmd) | Companion tutorial source (html) — a full, reproducible walkthrough of `bayes_met()` → `extr_outs()` → `prob_sup()` on the `maize` dataset |
| [`theme/probbreed.scss`](theme/probbreed.scss) | Custom revealjs theme used by the slide deck |
| [`images/`](images) | Lab and institutional logos used on the title slide |

## Rendering locally

Requires [Quarto](https://quarto.org/docs/get-started/) and R.

### Installing the required R packages

`ProbBreed` depends on `rstan`, which in turn requires a working C++ toolchain: **Rtools** on Windows, the **Xcode command-line tools** on macOS, or `build-essential` on Linux. Install that first, then, from an R console in the project directory:

```r
# Needed if your R installation has no default CRAN mirror configured yet
# (common on a fresh machine) -- otherwise install.packages() errors with
# "trying to use CRAN without setting a mirror" when run non-interactively.
options(repos = c(CRAN = "https://cloud.r-project.org"))

if (!requireNamespace("ProbBreed", quietly = TRUE)) {
  install.packages("ProbBreed")
}

if (!requireNamespace("tidyverse", quietly = TRUE)) {
  install.packages("tidyverse")
}

# Alternatively, the development version of ProbBreed from GitHub
# (pak resolves and installs dependencies faster than install.packages):
# install.packages("pak")
# pak::pak("saulo-chaves/ProbBreed")
```

The `install-packages` chunk at the top of [`hands_on_tutorial.qmd`](hands_on_tutorial.qmd) runs this same check automatically, so it only re-installs when a package isn't already available.

### Rendering the documents

```bash
quarto render presentation_probbreed.qmd
quarto render hands_on_tutorial.qmd
```

Rendering the presentation produces two files: `presentation_probbreed.html` (the audience copy, safe to publish) and `presentation_probbreed-speaker.html` (contains the multiplex control token — keep this one local, never publish it).

## References

- Chaves, S. F. S., Krause, M. D., Dias, L. A. S., Garcia, A. A. F., & Dias, K. O. G. (2024). ProbBreed: a novel tool for calculating the risk of cultivar recommendation in multienvironment trials. *G3: Genes\|Genomes\|Genetics*, 14(3), jkae013. <https://doi.org/10.1093/g3journal/jkae013>
- Dias, K. O. G., Santos, J. P. R., Krause, M. D., Piepho, H.-P., Guimarães, L. J. M., Pastina, M. M., & Garcia, A. A. F. (2022). Leveraging probability concepts for cultivar recommendation in multi-environment trials. *Theoretical and Applied Genetics*, 135(4), 1385–1399. <https://doi.org/10.1007/s00122-022-04041-y>
- Package documentation: <https://saulo-chaves.github.io/ProbBreed_site/>

## Authors

Wagner Faria Barbosa (Post-doctoral researcher) and Rhoda Ayanfeoluwa Ojo (Master student) — Quantitative Genetics and Statistical Learning Lab, UFV.
