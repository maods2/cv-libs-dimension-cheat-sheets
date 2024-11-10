# Computer Vision Libraries - Image Data Conventions

## Summary of the information in a **cheat sheet** format focusing on **data type**, **dimensions**, and **channels**:

| **Library**      | **Data Type**           | **Dimensions (Shape)**    | **Channels (Colors)**   |
|------------------|-------------------------|---------------------------|-------------------------|
| **OpenCV**       | `uint8`                 | `(h, w, 3)` (RGB/BGR) or `(h, w)` (Grayscale) | BGR (RGB for conversion) |
| **Pillow (PIL)** | `uint8`                 | `(h, w, 3)` (RGB) or `(h, w)` (Grayscale) | RGB (RGBA if transparent) |
| **TensorFlow**   | `uint8` or `float32`    | `(h, w, 3)` (RGB) or `(h, w)` (Grayscale) | RGB |
| **PyTorch**      | `uint8` or `float32`    | `(3, h, w)` (RGB) or `(1, h, w)` (Grayscale) | RGB |
| **Scikit-Image** | `float64` or `uint8`    | `(h, w, 3)` (RGB) or `(h, w)` (Grayscale) | RGB |
| **Imageio**      | `uint8`, `float32`, or `float64` | `(h, w, 3)` (RGB) or `(h, w)` (Grayscale) | RGB |

### Notes:
- **RGB** has 3 channels: **Red, Green, Blue**.
- **Grayscale** has 1 channel.
- Most libraries use **`uint8`** for 8-bit images (0-255), but they can use **`float32` or `float64`** for normalization or mathematical operations.

## Summary of **data types**, how much they store in memory, and which is the most common:

| **Data Type**    | **Memory Usage**          | **Description**                               | **Most Common in Computer Vision** |
|------------------|---------------------------|-----------------------------------------------|-----------------------------------|
| **`uint8`**      | 1 byte (8 bits) per value  | Stores integers from 0 to 255 (common for 8-bit images). | **Most common** for color and grayscale images. |
| **`float32`**    | 4 bytes (32 bits) per value| Single-precision floating-point number (0-1 after normalization). | Used for image normalization or neural networks. |
| **`float64`**    | 8 bytes (64 bits) per value| Double-precision floating-point number (0-1 after normalization). | Less common, but used for high-precision calculations. |
| **`int16`**      | 2 bytes (16 bits) per value| Integers from -32,768 to 32,767. Not commonly used for images. | Used in specific cases like scientific images or high-resolution image processing. |
| **`uint16`**     | 2 bytes (16 bits) per value| Integers from 0 to 65,535. Used for high-resolution images (e.g., medical images). | Less common, used in high-depth images (e.g., 16-bit images). |

### Summary:
- **`uint8`** is the most common type in computer vision, as it uses only 1 byte per value and is suitable for images with values between 0 and 255, such as RGB and grayscale images.
- **`float32`** is widely used in neural networks and for image normalization (scaled from 0 to 1).
- **`float64`** is used when high precision is needed for calculations, but it is not commonly used in images, except for some specific operations.
- **`int16`** and **`uint16`** are used in more specialized contexts, such as scientific or medical images requiring higher color depth.
