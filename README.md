# vids

This script lets you search videos platforms (YouTube , PeerTube and BitChute) with command line easily.

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
