# homework

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

# homework 02.08
    # Task 1
from django.db import models

class RestaurantInfo(models.Model):
    name = models.CharField(max_length=255)
    description = models.TextField()
    address = models.CharField(max_length=255)
    phone = models.CharField(max_length=20)
    email = models.EmailField()
    image = models.ImageField(upload_to='restaurant_images')

class CustomerReview(models.Model):
    name = models.CharField(max_length=255)
    review = models.TextField()
    rating = models.IntegerField(choices=[(i, i) for i in range(1, 6)])
    created_at = models.DateTimeField(auto_now_add=True)
