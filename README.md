from cs1robots import *
load_world("/home/tashe/worlds/harvest1.wld")
hubo = Robot()
hubo.set_trace("blue")
hubo.set_pause(0.1)
def turn_right():
    hubo.turn_left()
    hubo.turn_left()
    hubo.turn_left()
row = 1
while row <= 6:
    while hubo.front_is_clear():
        hubo.move()
        if hubo.on_beeper():
            hubo.pick_beeper()
    if row < 16:
        if row % 2 == 1:
            hubo.turn_left()
            hubo.move()
            hubo.pick_beeper()
            hubo.turn_left()
        else:
            turn_right()
            hubo.move()
            turn_right()
            if hubo.on_beeper():
                hubo.pick_beeper()
    row = row + 1
