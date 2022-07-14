![dzr logo](.github/.logo.svg)

# DZR: the command line deezer.com player

> ⚠️ For [legal reasons](https://github.com/github/dmca/blob/master/2021/02/2021-02-10-deezer.md) this project
> - does not contain any track decryption key
> - does not cache any tracks on your machine

## Preview
[![asciicast](https://asciinema.org/a/406758.svg)](https://asciinema.org/a/406758)

## Dependencies

- `mpv` for playback (because of `PLAYER="mpv -"` default env variable)
- `curl` for HTTP query
- `jq` for API parsing
- `dialog` for TUI
- `openssl` (or `openssl-tool` in Android) for track decryption

## Install

### From the AUR (Arch Linux)

```sh
yay -S dzr
```

### From [GURU](https://github.com/gentoo/guru) (Gentoo)

```sh
emerge --ask dzr
```

### From TAR file

Save into a `dzr-master` folder :

```bash
curl -sL github.com/yne/dzr/archive/master.tar.gz | tar xzf -
sudo mv dzr-master/dzr* /usr/local/bin
```

## Usage Examples

```sh
dzr             # welcome screen
dzr /artist/860 # browse deezer.com/en/artist/860
```

## Usage as HTTP server

```sh
mkdir -p cgi-bin && cp dzr* ./cgi-bin/
python3 -m http.server --cgi
```

You shall then be able to play from http : http://0.0.0.0:8000/cgi-bin/dzr?6113114

## Compatibility

This project has been tested on:
- Linux (Ubuntu 18.04/20.04 but other distrib shall work)
- OpenBSD (But any BSD shall work)
- Android (using [Termux](https://termux.com/) from F-droid)
- Window 10 using WSL 1/2 and running dzr as CGI server then browsing http://127.0.0.1:8000 from windows

Need more OS support ? Open an issue or a pull request.
