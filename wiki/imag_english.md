<!--
Meta Description: # Imag: Image Manipulation in Go ## Synopsis `imag` is a Go package that provides powerful image manipulation capabilities, allowing developers to cre...
Meta Keywords: imag, err, image, package, log
-->

# Imag: Image Manipulation in Go

## Synopsis
`imag` is a Go package that provides powerful image manipulation capabilities, allowing developers to create, modify, and process images efficiently and effectively within their Go applications.

## Documentation
The `imag` package is designed to simplify the process of image manipulation in Go. It offers a rich set of functions for tasks such as resizing, cropping, rotating, and applying filters to images. The package is built on top of Go's standard `image` and `image/color` packages, providing additional features and utilities to enhance image processing tasks.

### Purpose
The primary purpose of the `imag` package is to provide developers with a user-friendly interface for performing common image operations without requiring extensive knowledge of the underlying image processing algorithms.

### Usage
To use the `imag` package, first, import it in your Go file:

```go
import "github.com/yourusername/imag"
```

You can then utilize its functions to manipulate images as needed. The package supports various image formats such as PNG, JPEG, and GIF, making it versatile for different applications.

### Key Features
- **Resizing**: Change the dimensions of an image while maintaining its aspect ratio.
- **Cropping**: Remove unwanted parts of an image by specifying rectangular regions.
- **Filtering**: Apply various filters (e.g., grayscale, blur) to images for effects or enhancements.
- **Format Conversion**: Convert images from one format to another seamlessly.

## Examples
Here are some basic examples demonstrating how to use the `imag` package:

### Resizing an Image
```go
package main

import (
    "log"
    "os"

    "github.com/yourusername/imag"
)

func main() {
    img, err := imag.Load("input.jpg")
    if err != nil {
        log.Fatal(err)
    }

    resizedImg := imag.Resize(img, 800, 600)
    err = imag.Save(resizedImg, "output_resized.jpg")
    if err != nil {
        log.Fatal(err)
    }
}
```

### Cropping an Image
```go
package main

import (
    "log"
    "os"

    "github.com/yourusername/imag"
)

func main() {
    img, err := imag.Load("input.jpg")
    if err != nil {
        log.Fatal(err)
    }

    croppedImg := imag.Crop(img, 100, 100, 400, 400)
    err = imag.Save(croppedImg, "output_cropped.jpg")
    if err != nil {
        log.Fatal(err)
    }
}
```

### Applying a Filter
```go
package main

import (
    "log"
    "os"

    "github.com/yourusername/imag"
)

func main() {
    img, err := imag.Load("input.jpg")
    if err != nil {
        log.Fatal(err)
    }

    filteredImg := imag.GrayScale(img)
    err = imag.Save(filteredImg, "output_grayscale.jpg")
    if err != nil {
        log.Fatal(err)
    }
}
```

## Explanation
While `imag` provides a robust set of features, there are some common pitfalls to be aware of:

- **Image Format Compatibility**: Ensure the input image format is supported by the package. Unsupported formats may lead to errors during loading.
- **Aspect Ratio**: When resizing images, pay attention to the aspect ratio to avoid distortion. Use the provided functions to maintain the original proportions.
- **Error Handling**: Always check for errors when loading, manipulating, or saving images to prevent runtime panics or data loss.

## One Line Summary
`imag` is a Go package that simplifies image manipulation tasks such as resizing, cropping, and filtering, making it easy for developers to integrate image processing capabilities into their applications.