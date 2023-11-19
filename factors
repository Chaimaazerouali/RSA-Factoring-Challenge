#!/usr/bin/python3
import math
def print_factors_of_number(number):
    i = 1
    while i * i <= number:
        if number % i == 0:
            factor = number // i
            print("{:d}={:d}*{:d}".format(number, factor, i))
            break
        i += 1

def main():
    from sys import argv, exit, stderr

    if len(argv) != 2:
        stderr.write("Usage: ./factors <file>\n")
        exit()

    try:
        file = open(argv[1], "r")
    except FileNotFoundError:
        stderr.write("Could not find file {}, not exist\n".format(argv[1]))
    else:
        while True:
            line = file.readline()
            if not line:
                break
            line = int(line)
            print_factors_of_number(line)

    file.close()

main()
