# Image Editor

## Description
This program is an image editor that allows you to perform various operations on images. The code is organized into multiple `.h` files containing function and structure definitions, along with their corresponding `.c` files that contain the function implementations. The main file `image_editor.c` contains the main while loop and the operation that is read from the standard input. The program uses different functions from specific headers to perform various operations on the loaded image.

## Functionality
The program utilizes a while loop in the main function, which continues until the signaled operation is 'EXIT'. Within the loop, specific actions are taken based on the entered operation. If the operation is not recognized, an alert is printed stating that an 'Invalid command' was entered.

The program supports the following operations:

- **LOAD**: Loads an image from a file. It checks if the file was opened successfully and determines the format of the file (binary or ASCII). The image information is then extracted and stored in the corresponding data structures for further use.
- **SAVE**: Saves the current image to a file. The user can specify the file format (binary or ASCII) and provide a filename. The program calls the appropriate function to create the file and writes the image content into it.
- **SELECT**: Selects a specific area of the image. The user can provide coordinates to define the selection area. If no coordinates are provided or if 'ALL' is specified, the entire image is selected.
- **CROP**: Crops the image to the selected area. The program reallocates the pixel matrix to match the size of the selection and copies the selected area into it. The selection parameters are then updated to display the cropped image.
- **APPLY**: Applies various effects to the image. The user can specify the effect type (e.g., blur, sharpen, grayscale) as a parameter. The program applies the effect using the appropriate algorithm and updates the pixel matrix accordingly.
- **HISTOGRAM**: Generates a histogram for the image. The user can specify the number of bins for the histogram. The program calculates the frequency of pixels in each interval and prints a histogram representation using stars.
- **EQUALIZE**: Performs histogram equalization on a grayscale image. The program calculates the cumulative distribution function and adjusts the pixel values based on it, resulting in an equalized image.
- **ROTATE**: Rotates the image or a selected area by a given angle. The program checks if the selection is the whole image or a square within it. It then rotates the image or selection based on the angle provided by the user.

## Memory Management
The program deallocates the memory used by the image structures by calling the `free_img_rgb()` or `free_img_gs()` functions, depending on the image type that was loaded.

## File Structure
- `image_editor.c`: Contains the main while loop and the operation handling logic.
- `ops_skeleton.h` and `ops_skeleton.c`: Contains functions for reading and processing the user's input for various operations.
- `extract_info.h`: Contains functions for extracting image information from a file (format, dimensions, etc.).
- `rotate.h`: Contains functions for rotating the image or a selected area.
- Other headers and source files: Contains functions for specific operations such as saving, selecting, cropping, applying effects, generating histograms, and performing histogram equalization.

Hope you enjoy exploring my image editor! 😄
