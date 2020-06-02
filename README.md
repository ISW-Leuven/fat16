# FAT16
This repo contains a few things to help you find / calculate FAT16 properties, ...

## Table of contents
- [GPT Header](#gpt-header)
- [GPT Entry](#gpt-entry)
- [File Contents](#file-contents)

## GPT Header
![GPT Header Image](gpt_header.png)


## GPT Entry
- Size of cluster [BYTES] = `Bytes per sector` * `Sectors per cluster`
- Root Directory Address = `Small number of sectors` * `bytes per sector`
- Root Directory Size [BYTES] = `Number of possible root entries` * `Directory Entry size`  (often 32 bytes)
- Data Region Address = `Root Directory Address` + `Root Directory Size` [IN HEX]

![GPT Partition Image](gpt_partition.png)

## File Contents
- File contents = `Start of data region` + `cluster_size` * `(cluster_index - 2)`