# homework 25.07
# Task 1
def before_after(func):
def wrapper(*args, *kwargs):
    print("Action before calling the function")
    result = func(*args, *kwargs)
    print("Action after calling the function")
    return result
    return wrapper

@decoration(before_after):
def my_function(a, b):
    print(f"Calling func with args: {a}, {b}")
    return a + b
    my_function(2, 3)