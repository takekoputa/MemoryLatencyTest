# Memory Latency Test

Originally developed by [clamchowder](https://github.com/clamchowder/) and maintained here by other Chips & Cheese staff.

## Download

Get the latest (semi) stable release from the GitHub releases page [here](https://github.com/ChipsandCheese/MemoryLatencyTest/releases/). Windows and Linux binaries are both available. Bleeding edge binaries can be found in the artifacts of the Build with Meson workflow [here](https://github.com/ChipsandCheese/MemoryLatencyTest/actions/workflows/build-project.yml).


## Compile

Run the following:

```bash
$ mkdir build && cd build
$ meson ..
$ meson compile
```

The compiled binary will be in `build/src`.

## Compile with gem5 ROI annotations

To build the m5 library,

```bash
cd gem5/util/m5/build/"isa"/out # "isa" could be one of {x86, arm64, riscv64}
```

Run the following:

```bash
$ mkdir build && cd build
$ meson .. -Dgem5_include_dir=<path to gem5/include> -Dm5_build_path=<path to gem5/util/m5/build/"isa"/out>
$ ninja
```

