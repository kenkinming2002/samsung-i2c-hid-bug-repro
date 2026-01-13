# Instructions

## Build the relevant modules
Turns out you do not need to actually build the entire kernel to build a single
in-tree module. Wish I know that earlier.)
```
$ make -C /lib/modules/$(uname -r)/build M=$PWD/hid/drivers/hid/i2c-hid
```

## Testing
Just run the test script. Sudo is needed for loading/unloading modules. To
reproduce the bug, use the touchpad while the script is running to try to
trigger the race condition.
```
$ ./test
```
