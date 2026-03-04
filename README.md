# Pneumonia Detection

CNN-based pneumonia detection from chest X-ray images using TensorFlow/Keras.

## Project Files
- `cnn.ipynb`: Main notebook for data loading, model building, training, and evaluation.

## Requirements
- Python 3.10+
- TensorFlow / Keras
- NumPy
- Matplotlib

Install dependencies:
```powershell
py -m pip install tensorflow numpy matplotlib
```

## Dataset Structure
`flow_from_directory` expects this layout:

```text
chest_xray/
  train/
    NORMAL/
    PNEUMONIA/
  test/
    NORMAL/
    PNEUMONIA/
  val/
    NORMAL/
    PNEUMONIA/
```

Use absolute paths in the notebook to avoid `FileNotFoundError`.

Example:
```python
from pathlib import Path

data_root = Path(r"C:\Users\Visha\OneDrive\Documents\Pneumonia Detection\chest_xray")
train_dir = data_root / "train"
test_dir = data_root / "test"
```

## Running
1. Open `cnn.ipynb` in Jupyter.
2. Set dataset paths (`train_dir`, `test_dir`, optionally `val_dir`).
3. Run cells in order.

## Notes
- If you see `NameError: name 'layers' is not defined`, remove accidental `,layers` from model assignment and/or import with:
  ```python
  from tensorflow.keras import layers
  ```
- If you see path errors, verify directories exist with:
  ```python
  print(train_dir.exists(), test_dir.exists())
  ```
