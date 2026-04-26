# Project README

## Overview
This project is a C/C++ application that demonstrates how to create a simple user interface using custom data structures and scripts. The application supports building for different operating systems (Linux, Windows, Wine, and WebAssembly).

## Features
- Custom data structure for storing player information.
- Support for different build environments: Linux, Windows, Wine, and WebAssembly.

## Project Structure
```
Project/
├── build/              # .exe files produced by Main.c
├── libs/               # *.c for bin
├── lib/                # librarys for my own languages
├── code/               # scripts from my custom languages for example .rex, .ll, .omml
├── data/               # Datafile for example .txt or dumped files
├── assets/             # images and sound files
├── src/                # source code
│   ├── Main.c          # Entry point
│   └── *.h             # stand alone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
└── README.md           # This file
└── LICENSE
└── .gitignore
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: X11, ALSA
  - Windows: WINAPI
  - Wine: No additional libraries required
  - WebAssembly: Emscripten

## Build & Run
To build and run the project:

### For Linux
```sh
cd Project
make -f Makefile.linux all
make -f Makefile.linux exe
./build/Main.exe
```

### For Windows
```sh
cd Project
make -f Makefile.windows all
make -f Makefile.windows exe
start build\Main.exe
```

### For Wine
```sh
cd Project
make -f Makefile.wine all
make -f Makefile.wine exe
WINEPREFIX=~/wine64 WINEARCH=win64 wine build/Main.exe
```

### For WebAssembly (Emscripten)
```sh
cd Project
emcc src/Main.c -o build/Main.html -s WASM=1
python -m http.server 8000
# Open http://localhost:8000/build/Main.html in a web browser
```