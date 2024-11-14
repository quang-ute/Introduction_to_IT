# Basic shapes
```
import turtle

# Create a turtle object
t = turtle.Turtle()
t.speed(1)  # Set drawing speed (1-10)

# Draw a square
for i in range(4):
    t.forward(100)
    t.right(90)

# Move turtle to new position without drawing
t.penup()
t.goto(-150, 0)
t.pendown()

# Draw a triangle
for i in range(3):
    t.forward(100)
    t.right(120)

# Move turtle
t.penup()
t.goto(150, 0)
t.pendown()

# Draw a circle
t.circle(50)  # 50 is the radius

# Move turtle
t.penup()
t.goto(0, -150)
t.pendown()

# Draw a pentagon
for i in range(5):
    t.forward(100)
    t.right(72)  # 360/5 = 72 degrees

turtle.done()  # Keep window open
```
# Colorful Patterns
```
import turtle
from random import choice

# Create a turtle object
t = turtle.Turtle()
t.speed(8)

# List of colors to use
colors = ['red', 'blue', 'green', 'purple', 'orange', 'yellow']

# Multicolored line
for i in range(6):
    t.pencolor(colors[i])
    t.forward(50)

# Move turtle
t.penup()
t.goto(-150, 0)
t.pendown()

# Colorful spiral
for i in range(50):
    t.pencolor(colors[i % 6])  # Cycle through colors
    t.forward(i * 4)
    t.right(45)

# Move turtle
t.penup()
t.goto(150, 0)
t.pendown()

# Rainbow circles
radius = 30
for color in colors:
    t.pencolor(color)
    t.circle(radius)
    radius += 10

turtle.done()
```
# Sinographs
import turtle
import math

t = turtle.Turtle()
t.speed(0)  # Fastest speed
t.pensize(2)

# Simple Spirograph Pattern
def simple_spirograph():
    radius = 100
    for i in range(36):  # 360/10 = 36 iterations
        t.circle(radius)
        t.right(10)

# Move turtle to new position
t.penup()
t.goto(-150, 0)
t.pendown()

# Overlapping Circles
def overlapping_circles():
    colors = ['red', 'purple', 'blue', 'green', 'orange', 'yellow']
    for i in range(36):
        t.pencolor(colors[i % 6])
        t.circle(70)
        t.right(10)

# Move turtle
t.penup()
t.goto(150, 0)
t.pendown()

# Flower Pattern
def flower_pattern():
    for i in range(36):
        # Draw four circles for each petal
        for j in range(4):
            t.circle(40)
            t.right(90)
        t.right(10)  # Rotate for next petal

# More Complex Spirograph
def complex_spirograph():
    t.clear()  # Clear previous drawings
    R = 125  # Radius of the fixed circle
    r = 75   # Radius of the moving circle
    d = 125  # Distance from the pen to the center of the moving circle
    
    angle = 0
    for i in range(360):
        # Parametric equations of spirograph
        x = (R - r) * math.cos(math.radians(angle)) + d * math.cos(math.radians((R - r) * angle / r))
        y = (R - r) * math.sin(math.radians(angle)) - d * math.sin(math.radians((R - r) * angle / r))
        
        t.goto(x, y)
        if i == 0:
            t.pendown()
        angle += 1

# Run any of these patterns by uncommenting:

simple_spirograph()
# overlapping_circles()
# flower_pattern()
# complex_spirograph()

turtle.done()
