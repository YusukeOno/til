## How to rename a screenshot file in macOS

```
$ defaults write com.apple.screencapture name "ScreenShot"
$ killall SystemUIServer
```

## How to use Safari's PiP for YouTube

As with Safari, the first menu you'll get will be YouTube's right-click menu. So right click again.

## How to merge files horizontally

```
$ paste -d ' ' <(find ~/Develop/Git/til -type f -name "*.md") <(find ~/Develop/Git/til -type f -name "*.md")  | sed 's/^/diff /'
```

## How to input logo mark the Apple .

```option + Shift + k``` 
