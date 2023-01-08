>>>
**Project-Template**

Please use this template for your practical electronics project. (feel free to delete this section) 

You can find a quick guide in the following [cheat sheet](https://www.markdownguide.org/cheat-sheet/) or specific [gitlab style](https://docs.gitlab.com/ee/user/markdown.html) here

>>>


----

# Electronic game console

by: *Tangat Baktybergen and Towfiqur Rahman Khan*


**Faculty of Technology and Bionics**

***Rhine-Waal University of Applied Sciences***

Date: 20 October 2022

----

## Abstract

The goal of our project is to create a simple handheld gaming device (Gameboy) using dot matrix display which can be operated with some buttons.

The components are used to create this device:

- 2 8x8 dot matrix displays
- 3 shift registers
- 1 ATMega328p microcontroller unit
- 5 control buttons
- 1 buzzer

Among these 5 action buttons, 4 buttons used for movements (Up, Down, Right, Left) and an event button (Start, Reset). The buzzer produces sound during the game.


## Table of Contents

[[_TOC_]]

## 1 Introduction

Game Boy is an 8-bit handheld gaming console. The console features  dot-matrix screen with adjustable contrast, five game control buttons (four directional buttons and "START" / "SELECT"), a single speaker and uses microcontroller as physical media for games. The color scheme is made from two tones. Our Game Boy is bundled with two most iconic games “Snake” and “Tetris”.[1]

### 1.1	Background

The Game Boy game console developed and manufactured by Nintendo. It was first released in Japan on April 21, 1989, in North America later the same year, and in Europe in late 1990. It was designed by the same team that developed the Game & Watch series of handheld electronic games and several Nintendo Entertainment System (NES) games: Satoru Okada, Gunpei Yokoi, and Nintendo Research & Development 1.[1]

The Game Boy was designed by Nintendo's chief engineer Gunpei Yokoi and its Nintendo R&D1 team. Following the popularity of the Nintendo Entertainment System, he held a meeting with Nintendo president Hiroshi Yamauchi, saying that he could do a handheld system with interchangeable games. The original internal code name for the Game Boy is Dot Matrix Game, referring to its dot-matrix display in contrast to the preceding Game & Watch series (which Yokoi had created in 1980) that has segmented LCDs pre-printed with an overlay, limiting each model to only play one game. The initials DMG came to be featured on the final product's model number: "DMG-01". Satoru Okada and Yokoi led the development of the console, which led to disagreements. Yokoi felt that the console could be small, light, durable and successful and have a recognizable library of games. Shigesato Itoi visited Nintendo and conceived the name "Game Boy" for the console Yokoi was designing. The internal reaction to the Game Boy at Nintendo was initially very poor, earning it the derogatory nickname "DameGame" from Nintendo employees, in which dame (だめ) means "hopeless" or "useless" (dame originating as a term used in the game Go, meaning "meaningless territory").Henk Rogers brought the game Tetris to Nintendo of America and convinced its president Minoru Arakawa to port it for the new system so it can reach a wider audience. Arakawa agreed and as a result, the game was ultimately bundled with the Game Boy and the system was released in Japan in April 1989, North America in July, and in Europe in September the following year. Nintendo had spent $10 million on marketing the Game Boy.[1]


## 2	Literature review

On March 20, 1995, Nintendo released several special edition Game Boy models with colored cases, advertising them in the "Play It Loud!" campaign known in Japan as Game Boy Bros. Play It Loud! units were manufactured in red, green, black, yellow, white, blue, and clear (transparent), or sometimes called X-Ray in the UK. Most common are the yellow, red, clear and black. Green is fairly scarce but blue and white are the rarest. Blue was a Europe and Japan-only release, white was a Japanese majority release with UK Toys R Us stores also getting it as an exclusive edition to them. The white remains the rarest of all the Play it Loud colors. A rare, limited edition Manchester United Game Boy is red, with the logos of the team emblazoned on it. It was released simultaneously with the Play it Loud! handhelds in the United Kingdom. The Play It Loud's screens also have a darker border than the normal Game Boy.[1]

On July 21, 1996, Nintendo released the Game Boy Pocket for US$69.99: a smaller, lighter unit that required fewer batteries. It has space for two AAA batteries, which provide approximately 10 hours of gameplay. The unit is also fitted with a 3 volt, 2.35 mm x 0.75 mm DC jack which can be used to power the system. The Pocket has a smaller link port, which requires an adapter to link with the older Game Boy. The port design is used on all subsequent Game Boy models, excluding the Game Boy Micro. The screen was changed to a true black-and-white display, rather than the "pea soup" monochromatic display of the original Game Boy. Also, the Game Boy Pocket (GBP) has a larger screen than the Game Boy Color (GBC) that later superseded it. The GBP's screen has a 65 mm (2.56 in) diagonal, 48.5 mm (1.91 in) width, and 43.5 mm (1.71 in) height, compared to a 59 mm (2.32 in) diagonal for the GBC. Although like its predecessor, the Game Boy Pocket has no backlight to allow play in a darkened area, it did notably improve visibility and pixel response-time (mostly eliminating ghosting). The first version did not have a power LED. This was soon added due to public demand, along with new Game Boy Pocket units of different colors (released on April 28, 1997), some of them new to the Game Boy line. There were several limited-edition Game Boy Pockets, including a gold-metal model exclusive to Japan. The Game Boy Pocket was not a new software platform and played the same software as the original Game Boy model.[1]

A clear 'skeleton' Famitsu Model-F edition appeared in 1997, which had only 5,000 units released, and a clear yellow edition.[1]

The Game Boy Light was released on April 14, 1998, and only available in Japan. Like the Game Boy Pocket, the system was priced at ¥6,800. The Game Boy Light is slightly bigger than the Game Boy Pocket and features an electroluminescent backlight for low-light conditions. It uses two AA batteries, which give it approximately 12 gameplay hours with the light on and 20 with it off. It was available in two standard colors: gold and silver. It also received numerous special editions, including a clear 'skeleton' Famitsu 500 edition (Model-F02) with white buttons. This edition was also limited to 5000 units, like the first Model-F. Astro Boy edition with a clear case and a picture of Astro Boy on it, an Osamu Tezuka World edition with a clear red case and a picture of his characters and a solid yellow Pokémon Center Tokyo version.[1]

## 3	Theory
If necessary please present theory in this section.

This math is inline $`a^2+b^2=c^2`$.

## 4	Methodology

The matrix displays are controlled with shift registers. One of the shift registers is used to control all the rows and the other two shift registers in series for columns. The type of the Shift registers are serial in and parallel out. These shift registers have 8 output pins. So, each shift register take 8 row or 8 column control.

Each of the matrix display has 8 rows and 8 columns which perfectly fits to the 8 output pin of the shift register. Rows are combined into one shift register while columns have two separate shift registers in series to control. The rows of the matrix is anode and columns are cathode. The general idea is to keep both rows and columns high so there are no current to lit them. If we send low voltage to the columns, a certain ixj led turns on. Also, the display should be refreshed at certain period and turn off and on again so we can see all leds on the display.

As mentioned before there are 5 buttons for control purpose. Buttons are connected to ground. Resistors were not used to save some space and they are pulled internally using programming. ( Mb include code of internal pullup mode here)

The buzzer is simple tone generator as output device.

The microcontroller ATMega328p is implemented as it is in the Arduino device. It has 16 MHz external clock, powered by 3 x AAA batteries which runs at 4.5 V within standards. Additional empty pins are added for furher programming of the mcu without taking it from the pcb. The pins are at RX/TX and MOSI/MISO/RESET as SPI connection. 

This is an example how to include code snippet:
```python
def function():
    #indenting works just fine in the fenced code block
    s = "Python code"
    print s
```

Example how to draw a table:

| Left Aligned | Centered | Right Aligned |
| :---         | :---:    | ---:          |
| Cell 1       | Cell 2   | Cell 3        |
| Cell 4       | Cell 5   | Cell 6        |
| OpAmp 741    | 2        | 1.00          |


## 5	Results
Here you should present your results.

This is an example how to include image:
![alt text](resources/Open_Source_Hardware_(OSHW)_Logo_on_blank_PCB.jpg "Example Image")
(C) Altzone, CC BY-SA 3.0 <https://creativecommons.org/licenses/by-sa/3.0>, via Wikimedia Commons


## 6	Discussion

The project is successful. Device turns on after we press the "Start/Reset" button. Matrix display works perfectly and games are also functionning as desired. We can control the movements using the buttons. After finishing the game, the buzzer plays sounds too. We can also reset the game by pressing the "Start/Reset" button once again.


## 7	Concluding Comments

After successfully making our prototype, we can say that it is possible to implement a game card system using this device.The microcontroller on the board should read the game and play from a other microcontroller that plays the role of the game card. This system allows us to play different games without programming the main controller every time by which we can easily save more memory space.

## 8	References

* [1] https://en.wikipedia.org/wiki/Game_Boy
* [2] 

## 9	Appendices

