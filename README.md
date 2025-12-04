# Ideas in Motion

Old SGI demo setup to use CMake. Originally created by Mark J. Kilgard and Silicon Graphics, Inc.

## Building

This project uses CMake and includes freeglut as a Git submodule.

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

## License

Copyright (c) Mark J. Kilgard, 1995-1997.
Copyright (c) Silicon Graphics, Inc., 1993.

See individual source files for detailed copyright and permission notices.