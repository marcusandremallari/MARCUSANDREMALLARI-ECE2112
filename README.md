# ECE 2112: Advanced Computer Programming and Algorithms

## Overview
This repository contains the Jupyter Notebook submission for **Experiment 1: Introduction to Python Programming** in ECE 2112. The tasks cover foundational Python techniques including string manipulation, string slicing, built-in string methods, and extended sequence unpacking.

## 1. Word Rotation Problem  
Create a function named `rotate_word()` that accepts a non-empty string and shifts the first character to the end of the word while preserving the order and capitalization of the remaining characters.

**Implementation Logic & Methods Used:**
* **String Slicing (`[1:]`):** Extracts all characters starting from index 1 to the end of the string.
* **Indexing (`[0]`):** Accesses the very first character of the input string.
* **Concatenation (`+`):** Joins the remaining characters with the moved first character.


def rotate_word(text):
    # Slice from index 1 to the end, then append the first character
    return text[1:] + text[0]


# Test execution
print(rotate_word("python"))  # Output: ythonp
print(rotate_word("logic"))  # Output: ogicl
print(rotate_word("Code"))  # Output: odeC
print(rotate_word("A"))  # Output: A

## 2. Username Builder Problem

Create a function that accepts two strings representing a first name and a last name, cleans both inputs, and generates a standardized username separated by a period.

The following functions and methods were used in this problem:

* `.lower()` - A string method that converts all uppercase letters in the input string into lowercase letters.

  Example: `"Ana Maria".lower()` --> `'ana maria'`

* `.replace()` - A string method that replaces specified characters in a string. In this problem, it is used to strip all space characters (`" "`) by replacing them with an empty string (`""`).

  Example: `"ana maria".replace(" ", "")` --> `'anamaria'`

* **String Concatenation (`+`)** - Joins the processed first name, a period (`"."`), and the processed last name into a single username string.

  Example: `"anamaria"` + `"."` + `"deleon"` --> `'anamaria.deleon'`

These built-in string methods and operations were combined in order to create a single defined function that builds a valid username:

python
def make_username(first_name, last_name):
    # Convert names to lowercase and strip out spaces
    clean_first = first_name.lower().replace(" ", "")
    clean_last = last_name.lower().replace(" ", "")

    # Join the processed names using a period
    return clean_first + "." + clean_last


# Test execution
print(make_username("Ada", "Lovelace"))  # Output: ada.lovelace
print(make_username("Alan", "Turing"))  # Output: alan.turing
print(make_username("Ana Maria", "De Leon"))  # Output: anamaria.deleon


## 3. Bookend Swap Problem

Create a function that accepts a list containing at least two elements, unpacks the list into three parts (first, middle, and last), and returns a new list with the first and last elements swapped while maintaining the original sequence of the middle items.

The following functions and methods were used in this problem:

* **Extended Sequence Unpacking (`first, *middle, last`)** - A syntax feature that unpacks elements from an iterable into individual variables. The starred expression `*middle` captures all elements located between the first and last items into a separate sublist.

  Example: `first, *middle, last = [1, 2, 3, 4, 5, 6]` --> `first = 1`, `middle = [2, 3, 4, 5]`, `last = 6`

* **List Concatenation (`+`)** - Operates on list data types to combine multiple sublists into a single contiguous list. Enclosing `last` and `first` inside brackets converts them into single-element lists (`[last]` and `[first]`) so they can be merged with the `middle` sublist.

  Example: `[6]` + `[2, 3, 4, 5]` + `[1]` --> `[6, 2, 3, 4, 5, 1]`

These Python unpacking and list construction techniques were combined in order to create a single defined function that swaps the outer bookends of any given list:

python
def swap_bookends(items):
    # Unpack the first element, middle sublist, and last element
    first, *middle, last = items

    # Reconstruct and return the list with first and last elements swapped
    return [last] + middle + [first]


# Test execution
print(swap_bookends([1, 2, 3, 4, 5, 6]))  # Output: [6, 2, 3, 4, 5, 1]
print(
    swap_bookends(["red", "green", "blue"])
)  # Output: ['blue', 'green', 'red']
print(swap_bookends([8, 3]))  # Output: [3, 8]

Thank you for reading!
