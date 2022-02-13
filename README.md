# card-game

import turtle
import time
import random

wn = turtle.screen()
wn.bgcolour("black
wn.setup(800,600)
wn.title("Deck of simulator")

pen = turtle.Turtle()
pen.speed(0)
pen.hideturtle()

# create classes
class card():
    def __init__(self, name, suit):
        self.name = name
        self.suit = suit
        self.symboles = {"D", "C", "H", "S" }
        
   def print_card(self):
       print(f"{self.name}{self.symbols[self.suit]}")
       
   def render(self, x, y, pen):
       # draw border
       pen.penup()
       pen.goto(x, y)
       pen.colour("blue")
       pen.goto(x-50, y+75)
       pen.begin_fill()
       pen.goto(x+50, y+75)
       pen.goto(x+50, y-75)
       pen.goto(x-50, y-75)
       pen.goto(x-50, y+75)
       pen.end_fill()
       pen.penup()
       
       if self.name !+ "":
          # Draw suit in the middle
          pen.colour("white")
          pen.goto(x-18, y-30)
          pen.write(self.symbols[self.suit], False, font=("courier NEW", 48, "normal"))
          
          # Draw top left
          pen.goto(x-40, y+45)
          pen.write
