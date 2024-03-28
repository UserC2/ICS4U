# Settings & Configuration
**March 28, 2024**

Modern programs are becoming more *generic*, meaning that they can do a variety of different things based on their configuration.

To store this configuration, programs often use *key-value pairs* (a dictionary). File formats such as JSON or YAML can be used to store each key-value pair, which can be converted into a dictionary and read by the program.

## Dictionaries & Hash Functions
A sorted array can be used to store a dictionary within a program efficiently.
To sort the dictionary, each key is converted into a number (easy to compare) by a *hash function*.

A hash function takes some input (such as a string) and produces unique output (such as a number) based on the input.

A good hash function will produce unique output for all input given to it (and will produce the same output given the same input).