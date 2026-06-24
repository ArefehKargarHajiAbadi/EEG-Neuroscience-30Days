# Day 1: Data I/O and Metadata Extraction in MNE-Python

## 🎯 Objective
The goal of this day is to understand how to read standard clinical and research EEG formats (EDF, BDF, VHDR) using `MNE-Python` and extract essential metadata such as sampling frequency ($f_s$), number of channels, and signal duration.

## 🛠️ Tools Used
- `mne` (MNE-Python)
- `os` (for file path handling)

## 📝 Workflow
1. Implemented a custom `load_eeg_data` function to automatically select the appropriate `read_raw_*` method based on the file extension.
2. Utilized `preload=True` to load the data into RAM for faster subsequent processing.
3. Extracted metadata from the `raw.info` dictionary.
4. Calculated total signal duration using the formula: $T = \frac{N}{f_s}$ (where $N$ is the number of samples).

## ⚠️ Notes
- Clinical datasets often contain duplicate channel names (e.g., `T8-P8`). MNE handles this automatically by renaming them to ensure unique keys, which may generate a `RuntimeWarning`.
- **Data Privacy & Size:** The actual EEG datasets (e.g., `.edf` files) are added to `.gitignore` and are not pushed to this repository.
