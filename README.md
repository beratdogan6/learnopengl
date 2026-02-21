# learnopengl

A personal OpenGL learning project following [learnopengl.com](https://learnopengl.com).
Built with GLFW, GLAD, and OpenGL 3.3 Core Profile on Windows (MSYS2 ucrt64).

## Stack

| Library | Purpose |
|---------|---------|
| OpenGL 3.3 | Graphics API |
| GLFW | Window & input |
| GLAD | OpenGL function loader |

## Project Structure

```
learnopengl/
├── main.cpp          # entry point
├── src/
│   └── glad.c        # GLAD loader source
├── include/
│   ├── glad/         # GLAD headers
│   └── KHR/          # Khronos headers
└── CMakeLists.txt
```

## Build

**First time / after changing CMakeLists.txt:**
```bash
cmake -S . -B build && cmake --build build
```

**Normal rebuild:**
```bash
cmake --build build
```

**Run:**
```bash
./build/app.exe
```
