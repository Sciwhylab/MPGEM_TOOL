# MPGEM — Molecular Prediction of Gene Expression Matrix

MPGEM is a web tool that expands a partial gene expression matrix into a much larger one.
You supply expression values for a defined set of genes; a pre-trained deep learning model
predicts the values for the remaining genes and returns the two sets merged into a single matrix.

Developed and maintained by **SciWhy Lab**.

---

## Access

**https://mpgempre.streamlit.app**

The tool is freely available in any web browser. There is nothing to install, no account to create,
and no login required — open the link and start uploading. It works on desktop and mobile browsers,
though a desktop screen is more comfortable for reviewing large matrices.

Your uploaded file is processed for the duration of your session only. Results are yours to
download; nothing is stored after the session ends.

---

## What it does

The underlying model works from a fixed reference gene list. The first **12,712** genes in that
list form the model's input; every remaining gene in the list is predicted. Given a matrix covering
the input genes, MPGEM returns predicted expression values for the full reference set, so a
narrow measured matrix becomes a genome-scale one.

---

## Using the tool

The interface is organised as five tabs, worked through in order.

### 1. Upload & Validate

Upload your CSV. The tool previews it, reports how many samples and genes it contains, and shows
how many of your samples already appear in the MPGEM reference sample list versus how many are new.
It then checks your gene set against what the model requires and tells you whether you are ready to
proceed. The full list of required reference genes can be browsed here, and a correctly formatted
sample file is available for download if you want to see the expected layout first.

### 2. Predict

Once validation passes, run the model. The merged matrix of measured and predicted values is
generated and previewed.

### 3. Download

Export the complete matrix as a CSV.

### 4. Query

Filter the results before downloading — by gene name, by sample ID, or by both. The filtered subset
can be downloaded separately.

### 5. Tutorial

A walkthrough video and written instructions covering each of the steps above.

---

## Input format

A CSV file in which the first column holds sample IDs and every following column is a gene:

```
sample_id,A1BG,A1CF,A2M,...
sample_1,4.21,2.98,7.55,...
sample_2,3.87,3.10,7.02,...
```

Values should be normalized gene expression values. Gene names must use official HGNC symbols —
you can check yours with the
[HGNC Multi-Symbol Checker](https://www.genenames.org/tools/multi-symbol-checker/).

Column order does not matter; the tool reorders columns to the model's expected sequence for you.
Extra genes beyond the required set are permitted and simply ignored. If any required gene is
absent, the tool will not run the prediction and will list exactly which genes are missing so you
can correct the file.

---

## Output

A CSV indexed by your sample IDs, containing your original input genes alongside the predicted
genes. The file can be downloaded in full, or as a filtered subset via the Query tab.

---

## Contact and support

- Email: [shandar@sciwhylab.org](mailto:shandar@sciwhylab.org)
- Report a problem: [open an issue](https://github.com/SougataJana/MPGEM_PREDICTION_TOOL/issues/new)
- Source code: [SougataJana/MPGEM_PREDICTION_TOOL](https://github.com/SougataJana/MPGEM_PREDICTION_TOOL)
- Lab website: [shandarslab.org](http://shandarslab.org)

A contact panel with these links is also available from the button in the corner of the app.
