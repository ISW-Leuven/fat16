# FAT16
This repo contains a few things to help you find / calculate FAT16 properties, ...

## Table of contents
- [GPT Header](#gpt-header)
- [GPT Entry](#gpt-entry)
- [File Contents](#file-contents)
- [Boot Sector](#boot-sector)
-  - [Disk Layout](#disk-layout)

## GPT Header
![GPT Header Image](gpt_header.png)


## GPT Partition Entry
![GPT Partition Image](gpt_partition.png)

## File Contents
- File contents = `Start of data region` + `cluster_size` * `(cluster_index - 2)`

## Boot Sector
![Boot sector](boot_sector.png)

### Disk Layout
- Boot Sector Address [HEX] = `First LBA` (GPT Entry, DEC) * `512`
- Size of cluster [BYTES] = `Bytes per sector` * `Sectors per cluster`
- Root Directory Address = `Small number of sectors` * `bytes per sector`
- Root Directory Size [BYTES] = `Number of possible root entries` * `Directory Entry size`  (often 32 bytes)
- Data Region Address = `Root Directory Address` + `Root Directory Size` [IN HEX]


## Sources
- UCLL
- Pieter Philippaerts