# homework
# Task 1
def sequence_generator(first_value, n, func):

current_value = first_value
for i in range(n):
    yield current_value
    current_value =
func(current_value)

def square(x):
    return x*2
for value in sequence_generator(1, 5, square):
    print(value)

# Task 2
def memoise(func):


# Task 3
def apply_and_sum(data, func):
    return sum(func(x) for x in data)

numbers = [1, 2, 3, 4, 5]
 def square(x):
     return x*2

sum_of_squares =
apply_and_sum(numbers, square)
print(`Sum of elements of the resulting list`)
 