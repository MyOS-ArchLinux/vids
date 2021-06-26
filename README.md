# vids

A POSIX script that helps you search videos platforms (YouTube , PeerTube and BitChute) with command line easily.

### Requirements
- `fzf` / `dmenu` / `rofi` - menu & input 
- `jq` - JSON parsing
- `awk` - text processing
- `mpv` - video player
- `youtube-dl`

## Installation

```bash
git clone https://github.com/MyOS-ArchLinux/vids
cd vids/
sudo install -m755 vids /usr/local/bin/vids
```

## Usage
```bash
vids --option query

Options:
    -yt , --ytb  , --youtube      search using Youtube
    -pt , --prtb , --peertube     search using PeerTube
    -bc , --btct , --bitchute     search using BitChute
```
## Note
You may want to install [mpv-youtube-quality](https://github.com/jgreco/mpv-youtube-quality) to change video quality on the fly , and [mpv_sponsorblock](https://github.com/po5/mpv_sponsorblock) or [mpv_sponsorblock_minimal](https://codeberg.org/jouni/mpv_sponsorblock_minimal) to skip sponsored segments of YouTube videos automatically.
