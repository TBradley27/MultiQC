---
name: FLASh
url: https://ccb.jhu.edu/software/FLASH/
description: >
  FLASH (Fast Length Adjustment of SHort reads) is a very fast and accurate software tool to merge paired-end reads from NGS data.
---

The FLASh module parses the log messages generated by the [FLASh](https://ccb.jhu.edu/software/FLASH/) read merger. To create a log file, you can use `tee`. From the FLASh help:

```bash
flash reads_1.fq reads_2.fq 2>&1 | tee logfilename.log
```

The sample name is set by the first input filename listed in the log. However, this can be changed to using the first output filename (i.e. if you used FLASh's `--output-prefix=PREFIX` option) by using the following config:

```yaml
flash:
  use_output_name: true
```

The module can also parse the `.hist` numeric histograms output by FLASh.

Note that the histogram's file format and extension are too generic by themselves which could result in the accidental parsing a file output by another tool. To get around this, the MultiQC module only parses files with the filename pattern `*flash*.hist`.

To customise this (for example, enabling for any file ending in `*.hist`), use the following config change:

```yaml
sp:
  flash/hist:
    fn: "*.hist"
```
