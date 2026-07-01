# Reproducibility

The repository notebook was run sequentially in Google Colab from Cell 1
through Cell 32 with no stored execution errors.

## Colab procedure

1. Upload or open the notebook in Google Colab.
2. Connect to a standard Python runtime.
3. Select `Runtime → Restart session and run all`.
4. Confirm that Cell 31 prints `PROJECT COMPLETED SUCCESSFULLY`.
5. Cell 32 downloads the generated CSV archive.

## Random seeds

The main project seed is set to `42`. Separate sections add fixed offsets to
that seed, allowing simulations to be reproduced while remaining independent
across modules.

## Network-dependent data

Historical prices and FRED yields are downloaded when the notebook runs.
Vendor revisions or unavailable network requests can cause small differences
in future reruns.

## Local execution

The Google Colab download cell uses `google.colab.files`. Skip that cell outside
Colab. The remaining analysis uses ordinary Python packages listed in
`requirements.txt`.
