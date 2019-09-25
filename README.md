# latihanpy

# Membuat Game basic Dari Python

1. import aplikasi turtle untuk memunculkan graphic.
2. kemudian buat variabel ***wn*** screen/layar game tersebut dengan memanggil ***wn = turtle.Turtle()***, kemudian di beri warna dengan memanggil variabel yang kita buat yaitu wn.
3. membuat garis atau batasan.

# Hasil Program saya
 

'''python


import turtle
import os

# setup screen

wn = turtle.Turtle()
wn = turtle.Screen()
wn.bgcolor("black")
wn.title("Pesawat luar angkasa")


#Garis2nya

border_pen = turtle.Turtle()
border_pen.speed(0)
border_pen.color("white")
border_pen.penup()
border_pen.setposition(-300,-300)
border_pen.pendown()
border_pen.pensize(3)
for side in range(4):
    border_pen.fd(600)
    border_pen.lt(90)
border_pen.hideturtle()

#membuat pemain nya

player=turtle.Turtle()
player.color("blue")
player.shape("triangle")
player.penup()
player.speed(0)
player.setposition(0, -250)
player.setheading(90)

playerspeed = 15

# membuat musuhnya...
enemy=turtle.Turtle()
enemy.color("red")
enemy.shape("circle")
enemy.penup()
enemy.speed(0)
enemy.setposition(-200, 250)

enemyspeed = 2

#perpindahan pemainnya

def move_left():
    x = player.xcor()
    x -= playerspeed
    if x < -280:
        x = - 280
    player.setx(x)
    
def move_right():
    x = player.xcor()
    x += playerspeed
    if x < 280:
        x = 280
    player.setx(x)

#membuat keyboard pencetannya
turtle.listen()
turtle.onkey(move_left, "Left")
turtle.onkey(move_right, "Right")

#main game loop
while True:
    #perpindahan musuh
    x = enemy.xcor()
    x += enemyspeed
    enemy.setx(x)

    #perpindahan musuh back dn bawah
    if enemy.xcor() > 280:
        enemyspeed *= -1
    if enemy.xcor() < -280:
        enemyspeed *= -1

delay = raw_input("masukkan untuk selesai")

'''