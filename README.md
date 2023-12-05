# hipcub-benchmark

## Build the Customized Benchmark for Segmented Radix Sort
```bash
$ mkdir build && cd build
$ CXX=hipcc cmake ../. -DBUILD_TEST=OFF -DBUILD_BENCHMARK=ON -DGPU_TARGETS=gfx90a
$ make -j segmented16_radix_sort
```


## Run App
```bash
$ benchmark/segmented16_radix_sort --size 1287936
```

## Result
Docker: rocm/dev-ubuntu-22.04:5.6-complete

- [HIP] Device name: AMD Instinct MI210
- Running benchmark/segmented16_radix_sort
- Run on (128 X 2250 MHz CPU s)
- CPU Caches:
  - L1 Data 32 KiB (x128)
  - L1 Instruction 32 KiB (x128)
  - L2 Unified 512 KiB (x128)
  - L3 Unified 16384 KiB (x32)
- Load Average: 12.71, 7.02, 4.09

| Benchmark | Time | CPU | Iterations | UserCounters...|
| --------- | ---- | --- | ---------- | -------------- |
| sort_pairs<float, int>(~16 segments), descending/manual_time | 14.4 ms | 14.4 ms | 49| bytes_per_second=2.66979G/s items_per_second=358.333M/ |