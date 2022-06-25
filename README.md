# DL

**DL** is your ultimate file downloader.

## Getting Started

### Downloading

To download DL, it's as simple as cloning the repo.

```sh
$ git clone https://github.com/Python3-8/dl
...
$ cd dl
```

### Setup

The only thing you have to after downloading DL and entering the directory is install the requirements, which can be done easily with:

```sh
$ python3 -m pip install -r requirements.txt
...
```

Make sure you're on Python 3.7 or higher though, because older versions aren't supported.

## Features

DL isn't just any file downloader. DL lets you download files to, obviously, your file storage, but also `stdout` and your clipboard. Below are some examples.

**Example 1**

```sh
$ ./dl https://picsum.photos/150 picture.jpg
...
```

This is equivalent to `curl https://picsum.photos/150 -o picture.jpg`, which downloads the file at the given link and saves it to the output destination (`picture.jpg`). DL writes the contents in chunks of 32 bytes each to a cache file, and then moves the cache file to the specified destination.

**Example 2**

```sh
$ ./dl https://picsum.photos/150 -
...
```

This is equivalent to `curl https://picsum.photos/150`, which prints the contents (may be binary) of the file to `stdout`. DL writes the contents to `stdout` in chunks of 32 bytes each.

**Example 3**

```sh
$ ./dl https://picsum.photos/150 cb
...
```

This special feature downloads the file (into the RAM) and copies it to the clipboard.

**Example 4**

```sh
$ ./dl ~/test.txt test.txt
...
```

This is equivalent to `cp ~/test.txt test.txt`, which copies the file at `~/test.txt` to `test.txt` in the current working directory.

**Example 5**

```sh
$ ./dl ~/test.txt -
```

This is equivalent to `cat ~/test.txt` which writes the contents of the file at `~/test.txt` to `stdout`.

```sh
$ ./dl ~/test.txt cb
```

This special feature copies the contents of the file at `~/test.txt` to the clipboard. The file, when read, is read in chunks of 32 bytes each.

## Customization

To change DL's cache directory, set the environment variable `DL_CACHE_DIR` to the path to the directory where you want DL to cache files. Note that DL's cache files do not use space on your disk because they are moved, not copied, to the specified destination.
