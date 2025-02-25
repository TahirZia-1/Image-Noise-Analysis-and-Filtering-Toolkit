# NoisyVision: Image Noise Analysis & Filtering Toolkit

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.0+-green.svg)
![NumPy](https://img.shields.io/badge/NumPy-1.19+-yellow.svg)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.3+-red.svg)

A comprehensive image processing toolkit for analyzing noise effects and applying various filtering techniques to digital images. This project demonstrates the application and comparison of different noise models and filtering algorithms with visual and quantitative analysis.

## Features

- RGB to grayscale image conversion
- Implementation of different noise models:
  - Gaussian noise (with adjustable intensity)
  - Salt & Pepper noise (with adjustable probability)
- Application of multiple filtering techniques:
  - Mean filter (average filtering)
  - Median filter
  - Adaptive median filter
- Multiple kernel size options (3×3, 7×7, 15×15)
- Visual comparison of filtering results
- Quantitative analysis using PSNR (Peak Signal-to-Noise Ratio)

## Usage

The main functionality is provided as a Jupyter Notebook:

```bash
jupyter notebook image_processing.ipynb
```

Alternatively, you can run the Python script directly:

```bash
python image_processing.py
```

### Sample Code

```python
# Read an image
img_rgb = read_image('path/to/your/image.jpg')

# Convert to grayscale
img_gray = rgb_to_gray(img_rgb)

# Add noise
img_gaussian = add_gaussian_noise(img_gray.copy())
img_salt_pepper = add_salt_pepper_noise(img_gray.copy())

# Apply filters
filtered_image = apply_median_filter(img_gaussian, kernel_size=7)

# Calculate PSNR
psnr_value = calculate_psnr(img_gray, filtered_image)
print(f"PSNR: {psnr_value:.2f} dB")
```

## Results

### Noise Models

The project implements two noise models with adjustable parameters:

1. **Gaussian Noise**: Adds random values from a Gaussian distribution to each pixel
2. **Salt & Pepper Noise**: Randomly sets pixels to either black (0) or white (255)

### Filter Comparison

Different filters perform optimally for different noise types:

| Noise Type      | Best Filter         | Optimal Kernel Size |
|-----------------|---------------------|---------------------|
| Gaussian        | Adaptive Median     | 7×7                 |
| Salt & Pepper   | Median              | 3×3 / 7×7          |

### Sample Outputs

![Sample Filtering Results](sample_images/filter_comparison.png)

## Key Findings

1. **Noise Type Dependency**: Different filters perform better for specific noise types
2. **Kernel Size Tradeoff**: Larger kernels remove more noise but also blur image details
3. **Adaptive Approaches**: Adaptive filters generally provide the best balance between noise reduction and detail preservation
4. **Quantitative Analysis**: PSNR metrics align with visual quality assessments

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- OpenCV community for the image processing tools
- NumPy and SciPy for the scientific computing libraries
- Matplotlib for the visualization capabilities
