# FAT16
This repo contains a few things to help you find / calculate FAT16 properties, ...

## Table of contents
- [GPT Header](#gpt-header)
- [GPT Entry](#gpt-entry)
- [Boot Sector](#boot-sector)
-  - [Disk Layout](#disk-layout)
- [File & Directories](#files)
-  - [Time](#time)
-  - [Date](#date)
- [Sources](#sources)

## GPT Header
![GPT Header Image](gpt_header.png)


## GPT Partition Entry
![GPT Partition Image](gpt_partition.png)

## Boot Sector
![Boot sector](boot_sector.png)

### Disk Layout
- Boot Sector Address [HEX] = `First LBA` (GPT Entry, DEC) * `512`
- Size of cluster [BYTES] = `Bytes per sector` * `Sectors per cluster`
- Root Directory Address = `Small number of sectors` * `bytes per sector`
- Root Directory Size [BYTES] = `Number of possible root entries` * `Directory Entry size`  (often 32 bytes)
- Data Region Address = `Root Directory Address` + `Root Directory Size` [IN HEX]

## Files
![Files and directories](files_directories.png)

- File contents = `Start of data region` + `cluster_size` * `(cluster_index - 2)`

### Time
1. First 5 bits for hours
2. Next 6 bits for minutes
3. Last 5 bits for seconds (you have seconds multiply by 2 to get the value, eg.: 00011 => 3, 3 * 2 => 6 seconds)

### Date
1. First 7 bytes years since 1980 (eg.: if value in dec is 28, 1980 + 28 = 2008)
2. Next 4 bits for the month
3. Last 5 bits for the day

## Sources
- UCLL
- Pieter Philippaerts