# 🚆 LiDAR Clearance Envelope Checker

This Python project analyzes a LiDAR point cloud (`.e57` file) to detect points that violate a predefined clearance envelope along the main axis of the cloud.

---

## 🧰 Features

- 📥 Load and process `.e57` LiDAR files
- 🧮 Extract perpendicular slices using PCA
- 📐 Model a 2D clearance envelope (gabarit)
- 🚨 Detect collision/violation points across the full cloud
- 📤 Export results in CloudCompare-compatible `.txt` format

---

## 📂 Script Overview

1. **Import required libraries**
2. **Load and align the point cloud**
3. **Extract a perpendicular cross-section using PCA**
4. **Define a 2D clearance envelope**
5. **Detect violation points within the cloud**
6. **Export all results for visualization**

---

## 📦 Dependencies

Make sure you install the following libraries:

```bash
pip install pye57 open3d shapely pandas numpy
```

---

## 🖥️ Usage

1. Place your `.e57` file in the desired location.
2. Update the `e57_path` and `output_dir` variables in the script.
3. Run the script to:
   - Extract a perpendicular section
   - Detect violating points
   - Export results to `.txt` files

---

## 📁 Exported Files

| File                    | Description                                     |
|-------------------------|-------------------------------------------------|
| `section_slice.txt`     | Extracted perpendicular slice                  |
| `violations_full.txt`   | Points violating the clearance (colored red)   |
| `aligned_gabarit.txt`   | The clearance envelope transformed globally    |

---

## 📝 Customization

The default clearance envelope is defined as a simple 2D rectangle:

```python
clearance_polygon = Polygon([
    (-3.0, -3.0),
    (-3.0,  3.0),
    ( 2.0,  3.0),
    ( 2.0, -3.0)
])
```

You can change this to match your project requirements using any polygon supported by the `shapely` library.

---

## 📌 Notes

- The `.e57` file is **not committed to the Git repository** due to GitHub's 100 MB file size limit. It's recommended to use [Git LFS](https://git-lfs.github.com) or add the file to `.gitignore`.
- This script is suitable for prototyping or single-scan analysis. For batch processing or production usage, consider refactoring into modular functions or classes.

---

## 👤 Author

**Moussa ISSA**  
Capstone project using LiDAR data for clearance envelope analysis.
