# factorial.py

def factorial(n):
    """
    Calculate the factorial of a non-negative integer n.
    """
    if n < 0:
        return None
    elif n == 0:
        return 1
    else:
        result = 1
        for i in range(1, n + 1):
            result *= i
        return result

if __name__ == "__main__":
    num = int(input("Enter a non-negative integer: "))
    result = factorial(num)
    if result is not None:
        print(f"The factorial of {num} is {result}")
    else:
        print("Factorial is undefined for negative numbers.")
