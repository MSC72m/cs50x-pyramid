# Pyramid

## Project Description
This project is a solution to a CS50x problem set that involves creating a pyramid of a specified height. The height of the pyramid is provided by the user and must be between 1 and 8, inclusive. The pyramid is made up of hash (`#`) characters and spaces, formatted to look like the left-aligned Mario pyramid from the popular video game series.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)

## Installation
No special installation is required for this project. Ensure you have a C compiler like `gcc` installed.

## Usage
To compile and run the project, use the following commands:


make pyramid
./pyramid
You will be prompted to enter the height of the pyramid, which should be a number between 1 and 8.

Code Explanation
Main Function
``` C

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int height;
The #include <cs50.h> and #include <stdio.h> directives include the CS50 library and the standard input/output library, respectively.
int main(void) is the entry point of the program where the execution starts.
int height; declares a variable height to store the height of the pyramid provided by the user.
Input Validation
c
Copy code
    do
    {
        height = get_int("Enter the height of Pyramid (between 1 && 8): ");
    }
    while (height < 1 || height > 8);
The do...while loop repeatedly prompts the user to enter a valid height between 1 and 8.
get_int is a function from the CS50 library that prompts the user for an integer input.
The loop continues until the user enters a valid number within the specified range.
Constructing the Pyramid
c

    for (int rows = 0; rows < height; rows++)
    {
        // print spaces
        for (int spaces = height - rows - 1; spaces > 0; spaces--)
        {
            printf(" ");
        }

        // print each block
        for (int blocks = 0; blocks <= rows; blocks++)
        {
            printf("#");
        }
        printf("\n");
    }
}
``` 
The outer for loop (for (int rows = 0; rows < height; rows++)) iterates over each row of the pyramid, from 0 to height-1.
The inner for loop for spaces (for (int spaces = height - rows - 1; spaces > 0; spaces--)) prints the necessary spaces before the blocks in each row. The number of spaces decreases as the row number increases.
The inner for loop for blocks (for (int blocks = 0; blocks <= rows; blocks++)) prints the hash (#) characters. The number of blocks increases as the row number increases.
printf("\n"); moves the cursor to the next line after printing all spaces and blocks for the current row.
