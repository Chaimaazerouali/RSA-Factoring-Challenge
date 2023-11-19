#!/usr/bin/python3
import random
import math

def calculate_modular_pow(base, exponent, modulus):
    rt = 1
    while (exponent > 0):
        if (exponent % 2 != 0):
            rt = (rt * base) % modulus
        exponent = int(exponent / 2)
        base = (base * base) % modulus
    return rt

def find_prime_divisor(nm):
    if (nm == 1):
        return nm
    if (nm % 2 == 0):
        return 2

    x1 = (random.randint(0, 2) % (nm - 2))
    x2 = x1
    x3 = (random.randint(0, 1) % (nm - 1))

    a = 1
    while (a == 1):
        x1 = (calculate_modular_pow(x1, 2, nm) + x3 + nm) % nm
        x2 = (calculate_modular_pow(x2, 2, nm) + x3 + nm) % nm
        x2 = (calculate_modular_pow(x2, 2, nm) + x3 + nm) % nm

        a = math.gcd(abs(x1 - x2), nm)

        if (a == nm):
            return find_prime_divisor(nm)
    return a

def print_factors_of_number(number):
    divisor = find_prime_divisor(number)
    quotient = int(number / divisor)
    if divisor >= quotient:
        print("{:d}={:d}*{:d}".format(number, divisor, quotient))
    else:
        print("{:d}={:d}*{:d}".format(number, quotient, divisor))

def main():
    from sys import argv, exit, stderr

    if len(argv) != 2:
        stderr.write("Usage: ./factors <file>\n")
        exit()

    try:
        file_handle = open(argv[1], "r")
    except FileNotFoundError:
        stderr.write("Could not find file {}, not exist\n".format(argv[1]))
    else:
        while True:
            line = file_handle.readline()
            if not line:
                break
            line = int(line)
            print_factors_of_number(line)

    file_handle.close()

main()

