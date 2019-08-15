Miniz is a fast, small  zlib-replacement library.

The ESP32 has the low level features of miniz built into it's ROM, but lacks 
the higher level APIs. This library includes the higher level APIs while leveraging
the lower level functions stored in ROM. This results in a smaller firmware, and 
faster execution since most of the instructions aren't fetched from SPI Flash.

If you include the entire archive via the linker flags

```
COMPONENT_ADD_LDFLAGS = -Wl,--whole-archive -l$(COMPONENT_NAME) -Wl,--no-whole-archive
```

* miniz without ROM: 7036 Bytes
* miniz with ROM (this repo): 938 Bytes 

# Usage

In your project's `component/` directory, clone or add this repo as a submodule.

```
git clone https://github.com/joltwallet/esp_full_miniz.git
```
