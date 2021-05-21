# Profile MIOpenDriver GPU Kernel Time

## Execution

```bash
  $ bash ~/execute_miopen.sh --layout NCHW --direction 1 --dtype fp32 --no-xdlops < ~/llvm-project-mlir/mlir/utils/jenkins/miopen-tests/resnet50-miopen-configs 2>&1 | tee res.log
```

## Extract GPU Kernel Time

```bash
  $ cat res.log| grep -oP '\d+.\d+ ms' > parsed
```

## Append data at the end of csv

```bash
  $ paste --delimiter=',' res.csv parsed
```

