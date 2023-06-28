# Assembly Clock

This repository contains assembly code for a clock graphics program implemented in x86 assembly language. The code allows you to create a graphical representation of a clock on DOS using Assembly. Due to Windows protected mode not allowing assembly graphic commands to run, the clock.exe file needs to be executed on DOSBox.

## Group Members

1. Ali Hamza Malik
2. Ali Aqdas

## Source Code

The clock.asm file contains the assembly code for the clock graphics program, written by Ali Hamza Malik and Ali Aqdas.

## Code Explanation

The code is written in assembly language and uses the `model small` directive. It implements various procedures and macros to draw lines, circles, and plot pixels on the screen. The clock graphics are created by plotting lines and circles using these procedures.

The code includes the following main components:

- `PlotLine` macro: Draws a line between two given points with a specified color.
- `PlotLineLow` macro: Implements the line-drawing algorithm for lines with a shallow slope.
- `PlotLineHigh` macro: Implements the line-drawing algorithm for lines with a steep slope.
- `plotpixel` macro: Plots a pixel on the screen at the specified coordinates with a specified color.
- `drawcircle` macro: Draws a circle on the screen with a specified center, radius, and color.
- Math macros: `sinr` and `cosr` calculate the sine and cosine values of an angle in degrees.
- `quadrantloop` macro: Iterates through the four quadrants of a circle to draw markings at specific angles.
- `drawincrementedmarkings` macro: Draws incremented markings on the clock face.
- `printchar` macro: It is used to display a character at a specific location on the screen with a specified color.
- `gettime` proc: This procedure retrieves the current system time.
- `disptime` proc: Displays the current time (hours, minutes, and seconds) on the Analog Clock.
- `circlepoints` proc: It calculates and plots the points on a circle using the midpoint algorithm.


## Code Strucutre
<pre>
├── main proc
    ├── startvideomode macro
│   └── clockgraphics proc
│       │  `This part determines Time and plot H,M,S Hands based on Time using using sinr maco and PlotLinemacros`
│       ├── PlotLine macro 
│       │   ├── gettime proc
│       │   │    └──sinr macro
│       │   ├── PlotLineLow macro
│       │   │   └── plotpixel macro
│       │   └── PlotLineHigh macro
│       │       └── plotpixel macro
│       │   `This part creates the clock body, indicators and Clock Digits`
│       ├── drawcircle macro
│           ├── quadrantloop  macro
│           │    └── circlepoints proc
│           │        └── plotpixel macro
│           ├── printchar macro
│           └── drawincrementedmarkings macro
│ 
└── end
</pre>

## Usage

To run the clock program, follow these steps:

1. Install DOSBox on your system.
2. Copy the clock.exe file to a directory accessible from DOSBox.
3. Launch DOSBox and navigate to the directory where the clock.exe file is located.
4. Run the clock.exe file in DOSBox to execute the clock program.

## Disclaimer

```
The clock program is written in assembly language and uses graphic commands that may not be compatible with Windows' protected mode. Running the program in DOSBox provides a suitable environment for executing the assembly code and displaying the clock graphics.
```

####                                     Enjoy the clock program!