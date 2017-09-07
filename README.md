# mct (Music Convert & Tag)

This converts 16/24 bit `FLAC`, `M4A`, `MP4`, `SHN` or `WAV` audio files to (`VBR` 256kbps) or (`CBR` 320kbps) `MP3` using `lame` encoding.

If content is already `MP3`, it does not re-encode. However, it still proceeds with additional processing.

## Additional Processing

Aside from converting audio (if necessary), it proceeds with the following:

### Album Art

It looks to `folder.jpg` with the directory or the artwork image embedded within the first music file.

Then it optimizes the image, scaling it to `500px` while maintaining aspect ratio.

This results in a small-sized `jpeg` image that is embedded within each `MP3` file.

### ID3v2 Tagging

It preserves the text tags from each parent `FLAC` or `ALAC` file respectively, encoding them to `ID3v2 version 4` specification.

It asks to confirm the `artist` tag.

It asks to confirm the `album` tag, which it assumes is the parent folder of the current path. This is logically how studio albums are organized. This also works for live music where the folders are named and sorted by `YEAR.MON.DAY Venue, City, StateCode - CollectionName`.

## Installation

Install `ffmpeg` and `lame`, do:

```
$ sudo apt-get install ffmpeg lame libmp3lame0
```

From this path, symlink `mct` to user's bin directory:

```
ln -s `pwd`/mct ~/bin/
```

### Updates

To install updates; from this path, run:

```
git pull
```

## Usage

Open the path containing the files you wish to convert, then run:

```
mct
```
