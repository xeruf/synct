# synct

A simple [Syncthing REST API](https://docs.syncthing.net/dev/rest.html)
POSIX shell client tailored to my personal usage.

Can be extended with extra executables in the path like git.

## Installation

Simply move `synct` and any desired extension into your PATH.

### Dependencies
- grep curl tr paste
- bat for highlighted JSON pagination
- st-diff: stat git

## synct-unarchive examples
```sh
echo "1-projects/.sync/Archive/meetings.1.txt
1-projects/.sync/Archive/meetings.txt
data/.stversions/meeting~2020-01
meeting.sync-conflict-2021-1925-P5K
meeting.sync-conflict-2021-1925-PRK.txt" | synct-unarchive
```
yields
```sh
1-projects/meetings.txt
1-projects/meetings.txt
data/meeting
meeting
meeting.txt
```
