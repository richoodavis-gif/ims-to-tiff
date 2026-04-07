# ims-to-tiff
Convert ims file of imaris to tiff
- `convert_ims_to_tiff.py`

## Convert `.ims` to `.tiff`

Use `convert_ims_to_tiff.py` to convert Imaris `.ims` files in a folder to TIFF files.

Install dependencies:

```bash
pip install numpy tifffile h5py
```

Example:

```bash
python convert_ims_to_tiff.py /path/to/ims_folder --output-folder /path/to/output_tiff_folder
```
Simple mode: open `convert_ims_to_tiff.py` and edit this line:

```python
DEFAULT_INPUT_FOLDER = Path("/path/to/ims_folder")
```

Then run:

```bash
python convert_ims_to_tiff.py
```


Optional flags:
- `--input-folder /path/to/ims_folder` as flag-style input
- `--recursive` to search subfolders
- `--compression deflate` (default) or `--compression none`
- `--split-channels` to write one file per channel (default keeps all channels in one TIFF per timepoint)

If you run from Jupyter/Colab, notebook-injected `-f kernel-*.json` args are ignored by the script.

Output naming pattern by default: `<ims_stem>_t###.tiff` (all channels retained in the same TIFF per timepoint at ResolutionLevel 0).

If `--split-channels` is used: `<ims_stem>_t###_c###.tiff`.



