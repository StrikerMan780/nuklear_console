# nuklear_console

Console-like user interface for [Nuklear](https://github.com/Immediate-Mode-UI/Nuklear).

![nuklear_console](screenshot.png)

## Usage

``` c
#define NK_IMPLEMENTATION
#include "nukear.h"
#include "nuklear_console.h"

int main() {
    // Set up the console within the Nuklear context
    nk_console* console = nk_console_init(ctx);

    // Add some widgets
    nk_console_add_button(console, "New Game");
    nk_console* options = nk_console_add_button(console, "Options");
    {
        nk_console_add_button(options, "Some cool option!");
        nk_console_add_button(options, "Option #2");
        nk_console_add_button_onclick(options, "Back", nk_console_onclick_back);
    }
    nk_console_add_button(console, "Load Game");
    nk_console_add_button(console, "Save Game");

    // Render the console in a window
    nk_begin();
        nk_console_render(console);
    nk_end();

    // Clean it up
    nk_console_free(console);

    return 0;
}
```

## License

[MIT](LICENSE)
