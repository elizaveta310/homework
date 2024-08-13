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


    # homework 13.08

    #Task1
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}{% endblock %}</title>
    {% load static %}
    <link rel="stylesheet" href="{% static 'css/style.css' %}">
</head>
<body>
    <header>
        <h1>{% block header %}{% endblock %}</h1>
        <nav>
            <ul>
    <li><a href="{% url 'home' %}">Home</a></li>
    <li><a href="{% url 'menu' %}">Menu & Pricing</a></li>
    <li><a href="{% url 'chefs' %}">Master Chefs</a></li>
    <li><a href="{% url 'services' %}">Our Service</a></li>
    <li><a href="{% url 'contact' %}">Contact Us</a></li>
            </ul>
        </nav>
    </header>

    <main>
        {% block content %}{% endblock %}
    </main>

    <footer>
        <p>&copy; {{ restaurant.name }}</p>
    </footer>

    <script src="{% static 'js/script.js' %}"></script>
</body>
</html>

# Task 2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}{% endblock %}</title>
    {% load static %}
    <link rel="stylesheet" href="{% static 'css/style.css' %}">
</head>
<body>
    <header>
        <h1>{% block header %}{% endblock %}</h1>
        <nav>
            <ul>
                <li><a href="{% url 'home' %}">Home</a></li>
                <li><a href="{% url 'menu' %}">Menu & Pricing</a></li>
                <li><a href="{% url 'chefs' %}">Master Chefs</a></li>
                <li><a href="{% url 'services' %}">Our Service</a></li>
                <li><a href="{% url 'contact' %}">Contact Us</a></li>
            </ul>
        </nav>
    </header>

    <main>
        {% block content %}{% endblock %}
    </main>

    <footer>
        <p>&copy; {{ restaurant.name }}</p>
    </footer>

    <script src="{% static 'js/script.js' %}"></script>
</body>
</html>

{% extends 'base.html' %}

{% block title %}Home{% endblock %}

{% block header %}
    {{ restaurant.name }}
{% endblock %}

{% block content %}
    <h1>Добро пожаловать!</h1>
    <p>{{ restaurant.description }}</p>
    <img src="{{ restaurant.image.url }}" alt="Фото ресторана">
    <p>Наши шеф-повара готовят:</p>
    <ul>
        {% for dish in dishes %}
            <li>{{ dish.name }}</li>
        {% endfor %}
    </ul>
{% endblock %}



    created_at = models.DateTimeField(auto_now_add=True)
