# Quick Linux Translation (qltranslate)

Instruction how to configure quick translation for a word or whole phrase on Ubuntu Linux using Google translate engine.
It works by selecting text and pressing hotkeys in any windows (console, browser, text editor etc.).
![Translating a word](https://github.com/nitrogear/qltranslate/blob/master/docs/qltranslate-1.png?raw=true)
![Translating a text block](https://github.com/nitrogear/qltranslate/blob/master/docs/qltranslate-2.png?raw=true)

## Install dependency

```bash
$ apt-get install libnotify-bin xsel gawk
```

## Install translate-shell

```bash
$ wget git.io/trans
$ sudo mv ./trans /usr/local/bin
$ sudo chmod +x /usr/local/bin/trans
```

## Create wrapper scripts for translation

Create two files and make them executable

/usr/local/bin/qltr-word
```bash
#!/usr/bin/env bash
notify-send -u critical "$(xsel -o)" "$(trans -no-ansi :ru "$(xsel -o)")"
```
/usr/local/bin/qltr
```bash
#!/usr/bin/env bash
notify-send -u critical "$(xsel -o)" "$(trans :ru "$(xsel -o)" -brief)"
```

## Configure shortcuts

Open keyboard shortcuts settingsfrom Ubuntu menu and configure custom shortcuts to translate a word and text
![Configure shortcuts](https://github.com/nitrogear/qltranslate/blob/master/docs/qltranslate-3.png?raw=true)

## Quick translation

Select a word to translate and press your shortcut (alt+4 on screenshot) to get instant translation.
You also can select block of text and press configured shortcut to execure **qltr** (alt+5 on screnshot) and get translation for selected text
