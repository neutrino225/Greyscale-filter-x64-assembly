# Grayscale Filter x64 Assembly

## Introduction

Welcome to the Grayscale Filter x64 Assembly Project! This hobby project aims to provide a fast and efficient image processing tool to convert color images to stylish black and white using the power of x64 assembly language. The project is open-source and designed for easy integration into various image processing applications.

## How to Use

### Prerequisites

Before you begin, make sure you have the following installed:

- x64-based operating system
- NASM (Netwide Assembler) - for assembling the x64 assembly code

### Compiling the Grayscale Filter

To compile the grayscale filter, use the NASM assembler to assemble the x64 assembly code. Run the following command in your terminal:

```bash
nasm -f elf64 src/filter.asm -o filter.o
```

### Linking the Object File

Next, you need to link the object file generated from the assembly code to create an executable. Use the following command:

```bash
g++ src/main.cpp filter.o -o grayscale_filter -std=c++11 -no-pie -lX11 -lXext
```

### Running the Grayscale Filter

Once the executable is created, you can use it to convert your images to grayscale. Run the following command:

```bash
./grayscale_filter <input_image_name>
```

Replace `<input_image_filename>` with the filename of the color image you want to convert. The image will be saved to the `/imgs` directory with the prefix "output_"
   
### Example
    
Let's say you have a color image named "my_image.jpg" located in the `/imgs` directory of the project, and you want to convert it to grayscale and save it as "output_my_image.jpg". You can use the following command:

```bash
./grayscale_filter my_image.jpg
```
    
The grayscale filter will process the image and save the grayscale version as "output_my_image.jpg" in the `/imgs` directory.

## Makefile

The Makefile provided below allows you to easily build the Grayscale Filter x64 Assembly Project. It simplifies the build process and provides a convenient way to compile and organize the project files. To use the Makefile, follow the steps below:

### How to Use the Makefile

1. Open a terminal and navigate to the project directory containing the Makefile and source files.

2. To clean the project and remove the `build` directory, execute the following command:

```bash
make clean
```

3. To build the project, execute the following command:

```bash
make build
```
This command will assemble the `filter.asm` file using NASM and compile the main.cpp file with g++. The resulting executable will be named `prog`, and it will be placed in the `build` directory. Additionally, the `filter.o` object file will also be moved to the `build` directory.

Once the build process is complete, you will find the prog executable ready to use for converting your images to grayscale.

Now, you can run the executable to process your images as described in the previous sections.

```bash
build/prog <input_image_filename>
```
