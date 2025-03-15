# ShapeArt: Abstract Drawing Tool

<img src="screenshots/ShapeArt-1.png" alt="ShapeArt_logo" width="300">

## Overview
Drawing Shapes on Canvas is a Python CLI application designed to create and save images of shapes drawn on a canvas. The application, now known as **`ShapeArt`**, allows users to draw circles, rectangles, and squares of various dimensions and colors on a canvas and save the resulting image. It leverages Object-Oriented Programming (OOP) principles for modularity and code organization.

---

## Features
- **Canvas Creation**: Create a canvas of specified width, height, and color.
- **Draw Shapes**: Draw circles, rectangles, and squares of user-defined dimensions and colors on the canvas.
- **Save Image**: Save the canvas with drawn shapes as an image file.
- **User Input Validation**: Validate user inputs to ensure they are correctly formatted and within acceptable ranges.

---

## Technologies Used
- **numpy**: A library for numerical computations and array operations.
- **pillow**: A library for image processing in Python.
- **webcolors**: A module for working with web color names and converting between color formats.

---

## Setup
1. **Clone the Repository**:
    ```sh
    git clone https://github.com/emads22/ShapeArt.git
    ```
2. **Navigate to the Project Folder**:
    ```sh
    cd ShapeArt
    ```
3. **Ensure Python 3.x is Installed**: Check your Python version using:
    ```sh
    python --version
    ```
4. **Install Required Dependencies**:
    ```sh
    pip install -r requirements.txt
    ```

## Usage
1. **Run the Script**:
    ```sh
    python main.py
    ```
2. **Enter Canvas Information**:
    - Follow the prompts to enter the canvas width, height, and color.
3. **Draw Shapes**:
    - Choose whether to draw a circle, rectangle or square.
    - Enter the position, size, and color of the shape.
4. **Save Image**:
    - Once finished drawing, the canvas with shapes will be saved as an image file.

---

## Example
Here’s an example of how to use the Drawing Shapes on Canvas application:

1. **Run the script**:
    ```sh
    python main.py
    ```
2. **Input the following when prompted**:
    - **Canvas Width**: `600`
    - **Canvas Height**: `400`
    - **Canvas Color**: `blue`
    - **Shape to Draw**: `rectangle`
    - **Position (x, y)**: `100, 100`
    - **Width**: `200`
    - **Height**: `150`
    - **Color**: `green`
3. **The script will output**:
    ```sh
    --- Image with the drawn shapes created and saved successfully.
    You can find it here "path/to/image.png" ---
    ```

---

## Files Description
- **main.py**: The main script that runs the application and handles user input.
- **constants.py**: Defines constants used throughout the project, such as file paths.
- **app_utils.py**: Contains utility functions for validating user input (integer, color).
- **classes.py**: Defines the core classes for the application: `Canvas`, `Circle`, `Square`, and `Rectangle`.

---

## Dependencies
- **Pillow**: A Python Imaging Library that adds image processing capabilities to your Python interpreter.
- **webcolors**: A library to work with color names defined by the HTML and CSS specifications.

---

### ⬅ [🔗 Back to Premium Projects](../../README.md) 

