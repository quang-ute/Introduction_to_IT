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
