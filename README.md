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
          pen.write(self.name, False, font=("courier New", 48, "normal"))
          pen.goto(x-40, y+25)
          pen.write(self.symbols[self.suit], False, font=("courier New", 18, "normal"))
          
          # Draw buttom right
          pen.goto(x+30, y-60)
          pen.write(self.name, False, font=("courier New", 18, "normal"))
          pen.goto(x+30, y-80)
          pen.write(self.symbols[self.suit], False, font=("courier New", 18, "normal"))
          
class deck():
    def __init__(self):
        self.cards =[]
        
        names =("A", "K", "Q", "J", "T", "9", "8", "7", "6", "5", "4", "3", "2")
        suits = ("D", "C", "H", "S")
        
        for name in names:
            for suit in suits:
                card = card(name, suit)
                self.cards.append(card)
                
    def shuffle(self):
        random.shuffle(self.cards)
        
    def get_card(self):
        card = self.cards.pop()
        return card
        
    def reset(self):
        self.cards = []
        
        names = ("A", "K", "Q", "J", "T", "9", "8", "7", "6", "5", "4", "3", "2")
        suits = ("D", "C", "H", "S")
        
        for name in names:
            for suit in suits:
                card = card(name, suit)
                self.cards.append(card)
                
        self.shuffle()
        
# Create deck
deck = Deck()

# Shuffle deck
deck.reset()

# Render 5 cards (back) in row
start_x = -250
for x in range(5)
     card = Card("", "")
     card.render(start_x + x * 125, 0, pen)
     
     
time.sleep(5)

# Render 5 cards in a row
start_x =-250
for x in range(5)
    card = deck.get_card()
    card.render(start_x + x * 125, 0, pen)
    
wn.mainloop()
