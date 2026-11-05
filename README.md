# Local Binary Pattern (LBP) Texture Analysis

## Aim
To extract and visualize texture features from an image using the **Local Binary Pattern (LBP)** technique and analyze the texture distribution using a histogram.

## Overview
This notebook uses OpenCV, NumPy, Matplotlib, and scikit-image to perform Local Binary Pattern analysis.

The notebook performs these steps:

1. Imports the required Python libraries.
2. Loads the input image.
3. Checks whether the image was loaded successfully.
4. Converts the image from BGR to grayscale.
5. Defines the LBP radius and number of sampling points.
6. Computes the LBP texture pattern using the `uniform` method.
7. Displays the original grayscale image.
8. Displays the LBP texture pattern.
9. Plots a histogram showing the distribution of LBP codes.

## Technologies Used
- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- scikit-image (`skimage`)
- Jupyter Notebook / Google Colab

## Project Structure
```text
CV-Lab-LBP/
├── CVLAB09.ipynb
├── image16.jpg       
└── README.md
```

## Requirements
Install the required libraries:

```bash
pip install opencv-python numpy matplotlib scikit-image
```

## How to Run

### Option 1: Jupyter Notebook

1. Download or clone this repository.
2. Open a terminal in the project folder.
3. Install the required packages:
   ```bash
   pip install opencv-python numpy matplotlib scikit-image
   ```
4. Place `image16.jpg` in the project folder.
5. Open the notebook:
   ```bash
   jupyter notebook CVLAB09.ipynb
   ```
6. Update the image path in the notebook if needed.
7. Run all cells.

### Option 2: Google Colab

1. Upload `CVLAB09.ipynb` to Google Colab.
2. Upload `image16.jpg` to your Google Drive.
3. Ensure the image is located in the `COMPUTER VISION` folder, or update the path in the notebook.
4. Mount Google Drive if it is not already mounted:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
5. Run all cells.

## Important Code

### Load the Input Image

The notebook currently uses this Google Drive path:

```python
img = cv2.imread('/content/drive/MyDrive/COMPUTER VISION/image16.jpg')
```
### Convert to Grayscale

```python
gray_img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
```

### Set LBP Parameters

```python
radius = 1
n_points = 8 * radius
```

- `radius`: Radius of the circular neighborhood.
- `n_points`: Number of sampling points around the center pixel.

### Calculate Local Binary Pattern

```python
lbp = local_binary_pattern(
    gray_img,
    n_points,
    radius,
    method='uniform'
)
```

The notebook uses the `uniform` LBP method to calculate a texture pattern from the grayscale image.

### Histogram Analysis

The notebook plots a histogram of the calculated LBP values to show their frequency distribution.

## Expected Output
The notebook produces three visual outputs:

1. **Original Grayscale Image** – the input image converted to grayscale.
2. **LBP Texture Pattern** – the texture pattern generated using Local Binary Pattern.
3. **LBP Histogram (Texture Distribution)** – a histogram showing the frequency of LBP codes.

## Troubleshooting
If the notebook raises `FileNotFoundError`, check that:
- The input image is named exactly `image16.jpg`.
- The image exists at the path specified in `cv2.imread()`.
- Google Drive is mounted when running in Colab.

If a library import fails, install the missing package using the commands in the Requirements section.

## Notes
- The notebook requires the input image `image16.jpg`; add it to the repository so others can reproduce the experiment.
- The LBP parameters used are `radius = 1`, `n_points = 8`, and `method = 'uniform'`.
- The README describes the code currently present in the uploaded notebook.

## Author
Velaga Manikanta Sai.

241FA23016.

III-Data Science.
