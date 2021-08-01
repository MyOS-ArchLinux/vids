# vids

A POSIX script that helps you search videos platforms ([YouTube](https://www.youtube.com) , [PeerTube](https://sepiasearch.org) , [BitChute](https://www.bitchute.com), [LBRY](https://odysee.com) and [TED Talks](https://ted2srt.org/api/search)) with command line easily.

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
```
Usage:   vids [OPTIONS] query

Options:
  General Options:
    -h, --help                Print this help text and exit.
    -v, --version             Print program version and exit.

  Search:
    -p, --platform            
        ytrending             Youtbe Trending
        youtube               Youtbe
        peertube              PeerTube
        bitchute              BitChute
        lbry                  LBRY
        tedtalk               TED Talks

    -ytr, --ytrending         An alias for -p ytrending
    -yt, --youtube            An alias for -p youtube
    -pt, --peertube           An alias for -p peertube
    -bc, --bitchute           An alias for -p bitchute
    -ted, --tedtalk           An alias for -p tedtalk
    -lb, --lbry, --odysee     An alias for -p lbry

    --piped                   Use Piped; a privacy-friendly YouTube frontend.
    --no-piped                Do not use Piped.

    --nsfw                    Include nsfw videos. (WIP)
    --no-nsfw                 Do not include nsfw videos. (WIP)

  Menu Options:
    -m, --menu MENU          
        fzf                  supports multi-select with tab/shift-tab.
        dmenu                doesn't supports multi-select.
        rofi                 supports multi-select with shift-enter.

    --fzf                    An alias for --menu fzf
    --dmenu                  An alias for --menu dmenu
    --rofi                   An alias for --menu rofi

  Scripting Options:
    --print-json             print results json to stdout and exit.
    --print-link             print results links to stdout and exit.
    --print                  print results to stdout and exit.

  Environment variables:
    VIDS_DEFAULT_MENU        Default menu to use. (default: rofi -> dmenu -> fzf)
    VIDS_DEFAULT_PLATFORM    Default platform to use. (default: youtube)
    VIDS_DEFAULT_PLAYER      Default video player to use. (default: mpv)
    VIDS_SHOW_NSFW           Always include NSFW videos (default: false)
    VIDS_YOUTUBE_PIPED       Use Piped; the privacy-friendly YouTube frontend. (default: false )
    VIDS_PIPEDAPI_URL        Piped Instance API URL. (default: https://pipedapi.kavin.rocks )
    VIDS_PEERTUBE_URL        PeerTube Instance URL. (default: https://sepiasearch.org )

  Improve me on GitHub:
    https://github.com/MyOS-ArchLinux/vids
```
## Examples
- Search Youtube With fzf menu

    `vids --platform youtube --fzf Music`

- Search LBRY and print results to stdout

    `vids --lbry --print Music`

- Get a list of trending videos on youtube but don't expose your ip to youtube. (Use Piped)

    `vids --ytrending --piped`

- Scripting : Search PeerTube and extract titles

    `vids --peertube --print-json music | awk '{if (NR!=1) {print}}' | jq -r ".[]|.title"`

## Note
You may want to install [mpv-youtube-quality](https://github.com/jgreco/mpv-youtube-quality) to change video quality on the fly , and [mpv_sponsorblock](https://github.com/po5/mpv_sponsorblock) or [mpv_sponsorblock_minimal](https://codeberg.org/jouni/mpv_sponsorblock_minimal) to skip sponsored segments of YouTube videos automatically.
