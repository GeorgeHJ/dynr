# `dynr`
A convenience script for managing loudness-related metadata for music files.

## Usage
Run in a directory with `*.flac` files. Assumes the directory is an album.

## Supported file formats
Currently only `*.flac` is supported

## Dependencies
* `dr14_tmeter`
* `metaflac`
* GNU `sleep`

## Code style
Uses POSIX shell, verified by `shellcheck`. Most of the heavy lifing is done by the programs, so there's no need for bashisms.

Commands with weakly defined behaviour are avoided, see the spinner function:
```sh
spinner() {
	printf "%s" "$1"
	while true
	do
		printf "%s\b" "-"
		sleep 0.1
		printf "%s\b" \\
		sleep 0.1
		printf "%s\b" "|"
		sleep 0.1
		printf "%s\b" "/"
		sleep 0.1
	done
}
```
No `echo`!

## To do
* [ ] Refactoring
* [ ] Use `loudgain`
* [ ] Beets integration for optional `beet update`
