# Binary-Product
Given an integer n, find if it can be represented as the product of some (might be same) binary decimal numbers?  Binary decimal number is if it is a positive integer and all digits in its decimal notation are either 00 or 11. For example, 10, 101, 11101, 101 is a binary decimal, while 1020110201 and 78, 77, 31 are not.


def main():
    n = int(input())
    result = "Yes" if can_be_represented(n) else "No"
    print(result)

def can_be_represented(n):
    for i in range(1, n // 2 + 1):
        if is_binary_decimal(i) and n % i == 0 and is_binary_decimal(n // i):
            return True
    return False

def is_binary_decimal(num):
    num_str = str(num)
    for c in num_str:
        if c != '0' and c != '1':
            return False
    return True

if __name__ == "__main__":
    main()
