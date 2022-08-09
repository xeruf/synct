# synct

A simple [Syncthing REST API](https://docs.syncthing.net/dev/rest.html)
POSIX shell client tailored to my personal usage.

Can be extended with extra executables in the path like git.

`synct-diff` is the most notable extension -
it can recursively discover Syncthing sync-conflicts
and run various operations to handle them.

## Installation

Simply move `synct` and any desired extension into your PATH.

I maintain an AUR package `synct-git` for it, too.

### Dependencies
- grep curl tr paste
- bat for highlighted JSON pagination
- st-diff: stat git

## Testing

`dif` is a simple helper script to check if the system-wide installed binaries 
match the versions in the repo.

### synct-unarchive examples

A helper to remove different suffixes for archived/.
It also enables `synct-diff` to operate on editor backup files from vim, emacs and the like
as well as Resilio Sync (formerly BTSync) archives.

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
