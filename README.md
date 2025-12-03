# Ideas in Motion

Old SGI demo setup to use CMake. Originally created by Mark J. Kilgard and Silicon Graphics, Inc.

## Building

This project uses CMake and includes freeglut as a Git submodule.

### Prerequisites

- CMake 3.15 or higher
- C compiler (MSVC, GCC, or Clang)
- OpenGL development libraries

### Build Instructions

```bash
# Clone the repository with submodules
git clone --recursive https://github.com/YOUR_USERNAME/ideas.git
cd ideas

# Or if already cloned, initialize submodules
git submodule update --init --recursive

# Create build directory
mkdir build
cd build

# Configure and build
cmake ..
cmake --build .
```

## Usage

```bash
./ideas [options]

Options:
  -a              Auto-run (loop forever)
  -m              Multisample (antialiasing)
  -d              Single buffer mode
  -r WIDTHxHEIGHT Set window resolution (e.g., -r 800x600)
  -s{1-4}         Set animation speed (1=slow, 4=fastest)
```

### Controls

- **ESC**: Quit
- **1-4**: Control animation speed
- **Any other key**: Pause/resume
- **Left click**: Restart animation

## License

Copyright (c) Mark J. Kilgard, 1995-1997.
Copyright (c) Silicon Graphics, Inc., 1993.

See individual source files for detailed copyright and permission notices.

## Credits

- Original demo by Mark J. Kilgard
- Silicon Graphics, Inc.
- FreeGLUT library
