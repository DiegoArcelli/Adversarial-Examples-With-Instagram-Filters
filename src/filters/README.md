# Scalable-Instagram-Filters
Implementation of some Instagram filters which can be scaled with respect to two parameters. The implementation of the filters is heavly inspired from this repository: https://github.com/akiomik/pilgram.

## Description
The repository contains the implementation of the follwing filters:

* Hudson
* Stinson
* Slumber
* Perpetua
* Rise

The code of the filter is contained in the file `filters.py`. Each filter can be scaled with respect to the follwing parameters:
* Intensity ($\alpha$): which indicates the strenght by which the effects of the filter are applied to the original image
* Strength ($s$): a value that must be between 0 and 1, and it's used to compute a weighted sum between the original image and the filtered image. For example if the orinal image is denoted with $I$, the filtered image is denoted with $F$ and the value of the intensity parameter is denoted with $s$, then the output image will be: $F\cdot s + I\cdot(1-s)$

Morover there are some basic image trasformation in the file `transformations.py` which are scalable with respect to the same two parameters of the filters. These transformations are:

* Constrant change
* Brightness change
* Saturation change
* Sharpness
* Gamma correcction
* Sepia effect
* Noise
* JPEG compression
* Blur effect


## Usage
To apply the filters to a given the `main.py` file can be executed using as arguments:
- `--input`, `-i`: the path to the image to which the filters will be applied
- `--output`, `-o`: the path of the output image
- `--filters`, `-f`: the sequence of filters to apply to the input image with the corresponding values of the strenght and intensity parameters

The sequence of filters must follow the following structure:

`filter_name_1 alpha_1 s_1 ... filter_name_n alpha_n s_n`

For instance if we want to apply the filters stinson and hudson using for both a value $\alpha$ =  1.2 and a value of $s$ = 0.5, we can execute the command:

`python main.py -i input.jpg -o out.jpg -f stinson 0.5 1.2 hudson 0.5 1.2`

