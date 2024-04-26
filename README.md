# Usage
There should be a folder for each piece of hardware. Hardware is grouped by the style of hardware.

This is easily used with the [benchmark_compare.sh](https://github.com/wolfSSL/wolfssl/blob/master/scripts/benchmark_compare.sh) script.

## Generating benchmarks
Typically, you would compile wolfSSL and put the output of `wolfcrypt/benchmark/benchmark` into a file. Essentially do the following:
```
OUTFILENAME=outfile.csv; echo "wolfSSL version: $(git describe --tags 2>/dev/null || git branch --show-current)" > ${OUTFILENAME} && \
           echo "./configure $(./config.status --config)" >> ${OUTFILENAME} && \
           ./wolfcrypt/benchmark/benchmark -csv >> ${OUTFILENAME}
```

This will put out the commit version of wolfSSL as well as the configuration parameters.

