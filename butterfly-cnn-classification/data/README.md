# Butterfly Dataset Access

The project classifies five butterfly categories. The images and raw annotations were supplied for university coursework and are excluded because public redistribution permission has not been confirmed.

The cleaned dataset contained 113 usable images: Mourning Cloak 38, Sleepy Orange 37, Atala 35, Sootywing 2 and Gold Banded 1. Users must obtain the data lawfully. Set `BUTTERFLY_DATA_DIR` to a directory containing:

```text
Train_label.csv
Test_label.csv
train/
```

The notebook writes cleaned annotations to `processed/train-labels-cleaned.csv` without deleting or modifying source images. No public licence or download link is asserted here.
