# A very simple snake game
# By aceking007

# Imports
import turtle
import time #we need this library to  use a delay so we could see movements
import random



delay = 0.1 #Makes movements visible


# Set up the screen
wn = turtle.Screen()
wn.title('Best Snake Game Ever')
wn.bgcolor("#f2d1c9")
wn.setup(width=600, height=600)
wn.tracer(3)  # Turns off screen updates

# Snake head
head = turtle.Turtle()
head.speed(1) # 0 is the maximum animation speed of turtle module
head.shape("circle")
head.color('#2a4c70')
head.penup()
head.goto(0,0)
head.direction = 'stop'

# Snake Food
food = turtle.Turtle()
food.speed(0) # 0 is the maximum animation speed of turtle module
food.shape("square")
food.color('#a0bd7d')
food.penup()
food.shapesize(0.5, 0.5)
food.goto(random.randint(-280,280),random.randint(-280,280))

#Segments
segments = []

 

# Functions that move snake in response to keyboard keys
def go_up():
    head.direction = "up"
def go_down():
    head.direction = "down"
def go_left():
    head.direction = "left"
def go_right():
    head.direction = "right"

# Function that helps the snake move
def move():
    if head.direction == "up":
        y = head.ycor()
        head.sety(y+20)
    if head.direction == "down":
        y = head.ycor()
        head.sety(y-20)
    if head.direction == "left":
        x = head.xcor()
        head.setx(x-20)
    if head.direction == "right":
        x = head.xcor()
        head.setx(x+20)


### Keyboard bindings
wn.listen()
wn.onkeypress(go_up, 'Up')
wn.onkeypress(go_down, 'Down')
wn.onkeypress(go_left, 'Left')
wn.onkeypress(go_right, 'Right')

### Loop that runs the game code
while True:
    # Updates the window repeatedly
    wn.update()
    # Move the snake in the game
    move()

   

    # Check if the snake eats the food
    if head.distance(food) < 20:
        # Move the food to a random spot
        food.goto(random.randint(-290,290),random.randint(-290,290))
        # Add a segment
        new_segment = turtle.Turtle()
        new_segment.speed(0)
        new_segment.shape("circle")
        new_segment.color("#f2d272")
        new_segment.penup()
        segments.append(new_segment)
    for index in range(len(segments)-1, 0, -1):
        x = segments[index-1].xcor()
        y = segments[index-1].ycor()
        segments[index].goto(x,y)
        segments[index].shape("circle")
    # Move segment 0 to the head
    if len(segments) > 0:
        x = head.xcor()
        y = head.ycor()
        segments[0].goto(x,y)
        segments[0].color("#2a4c70")
    # Check for collision
    if head.xcor() > 290 or head.xcor() < -290 or head.ycor() > 290 or head.ycor() < -290:
        time.sleep(1)
        head.goto(0, 0)
        head.direction = "stop"
        

      
    

    # Delay so that we can see things move
    time.sleep(delay)

# Makes the window visible and runs everythings
wn.mainloop()
