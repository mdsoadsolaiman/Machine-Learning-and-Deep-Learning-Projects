# Blood-Cell Dataset Access

The project uses eight classes: basophil, eosinophil, erythroblast, immature granulocyte, lymphocyte, monocyte, neutrophil and platelet. The university-provided medical images are excluded because redistribution permission has not been confirmed.

Users must obtain the data lawfully and set `BLOOD_CELL_DATA_DIR` to:

```text
train/
  <class-name>/
test/
```

The inspected source contained 3,200 labelled training images and 1,000 unlabelled test images. Test accuracy cannot be calculated without ground-truth test labels. `class-map.json` documents the output mapping but does not license the images.
