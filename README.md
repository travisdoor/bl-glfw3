# GLFW3 for BL
GLFW3 wrapper for BL.

# Installation
## Windows

Clone the repository into the `bl` API folder. Use `blc -where-is-api` to get correct path.
```bash
cd path/to/api
git clone https://github.com/travisdoor/bl-glfw3.git glfw3
```

## Linux

Clone the repository into to the `bl` API folder.
```bash
cd $(blc -where-is-api)
git clone https://github.com/travisdoor/bl-glfw3.git glfw3
```

## macOS
Clone the repository into to the `bl` API folder.
```bash
cd $(blc -where-is-api)
git clone https://github.com/travisdoor/bl-glfw3.git glfw3
```
Install `glfw3` development package with your favorite package manager.
```bash
brew install glfw
```

# Example
Minimal glfw3 application in `example` folder. Use `blc -b` to compile.
```rust
#import "glfw3"

TITLE :: "GLFW";

main :: fn () s32 {
    Glfw.Init();
    defer Glfw.Terminate();

    window :: Glfw.CreateWindow(800, 600, TITLE.ptr, null, null);
    defer Glfw.DestroyWindow(window);
    Glfw.MakeContextCurrent(window);
    loop Glfw.WindowShouldClose(window) == 0 {
        Glfw.PollEvents();
        Glfw.SwapBuffers(window);
    }
    return 0;
}
```
