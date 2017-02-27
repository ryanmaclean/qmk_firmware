Maxipad keyboard firmware

## Quantum MK Firmware

For the full Quantum feature list, see [the parent readme.md](/readme.md).

If you are using a pro micro then make sure to enable USE_PRO_MICRO in the makefile
Change the config.h pinout to match your mcu!!

Download or clone the whole firmware and navigate to the keyboards/maxipad folder. Once your dev env is setup, you'll be able to type `make` to generate your .hex - you can then use the Teensy Loader to program your .hex file. 

Depending on which keymap you would like to use, you will have to compile slightly differently.

### Teensy

The default `config.h` file is for Pro Micro. For use with Teensy boards, make sure to comment out the Pro Micro section, and uncomment the Teensy section: 

```
//Pro micro pinout
    //#define MATRIX_ROW_PINS { B6, B2, B3, B1, F7 }
    //#define MATRIX_COL_PINS { F4, C6, D7, F5, B4, B5 }
    //#define UNUSED_PINS
//Teensy 2 pinout
     #define MATRIX_ROW_PINS { B6, F7, B2, B3, B1 }
    #define MATRIX_COL_PINS { F6, C6, D7, F5, B4, B5 }
    #define UNUSED_PINS
```

### Default

To build with the default keymap, simply run `make`.


### Other Keymaps
Several version of keymap are available in advance but you are recommended to define your favorite layout yourself. To define your own keymap create file named `<name>.c` and see keymap document (you can find in top readme.md) and existent keymap files.


To build the firmware binary hex file with a keymap just do `make` with a keymap like this:

```
$ make [default|jack|<name>]
```

Keymaps follow the format **__\<name\>.c__** and are stored in the `keymaps` folder.
