# Calcium imaging analysis

This repository contains the code used for calcium-imaging data extraction and analysis in the associated manuscript.

## Files

- `Data_extraction.ipynb` performs motion correction using NoRMCorre, AOI extraction using CNMF-E, component evaluation, and fluorescence-trace export.
- `Astrocyte_Peak_Analysis.ipynb` performs Gaussian filtering, baseline normalization, calcium-event detection, and calculation of event counts and integrated fluorescence activity.

## Analysis workflow

1. Motion correction was performed using NoRMCorre in CaImAn.
2. AOIs and fluorescence traces were extracted using CNMF-E.
3. Calcium events were detected using `scipy.signal.find_peaks`.
4. AOI activity was quantified as the integrated fluorescence signal during the analysis period using `numpy.trapz`.
5. Summary values were exported to GraphPad Prism for normalization, calculation of percentage changes, statistical analysis, and figure preparation.

## Key parameters

- Imaging rate: 2 frames per second
- Gaussian filter sigma: 3
- Minimum peak distance: 35 frames
- Peak threshold: mean plus 1 standard deviation
- Minimum peak prominence: 15
- Analysis window: 3 minutes

## Input files

- TIFF files containing calcium-imaging recordings
- CSV files containing extracted fluorescence traces

Input data files are not included in this repository.

## Software

- Python 3
- CaImAn
- NumPy
- pandas
- SciPy
- matplotlib
- OpenCV
- Bokeh
- HoloViews
- GraphPad Prism 8

## Notes

`Data_extraction.ipynb` was adapted from the CaImAn CNMF-E demonstration pipeline. Statistical analyses and figure preparation were performed manually using GraphPad Prism.