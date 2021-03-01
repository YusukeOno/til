# macOS Tips

- [macOS Tips](#macos-tips)
  - [How to rename a screenshot file in macOS](#how-to-rename-a-screenshot-file-in-macos)
  - [How to use Safari's PiP for YouTube](#how-to-use-safaris-pip-for-youtube)
  - [How to merge files horizontally](#how-to-merge-files-horizontally)
  - [How to input logo mark the Apple .](#how-to-input-logo-mark-the-apple-)
  - [How to deal with errors when starting VS Code](#how-to-deal-with-errors-when-starting-vs-code)
  - [How to use the sips command](#how-to-use-the-sips-command)
    - [PNG image profile check](#png-image-profile-check)
  - [How to use the Snap Camera on Microsoft Teams Mac OS client](#how-to-use-the-snap-camera-on-microsoft-teams-mac-os-client)

---

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

## How to deal with errors when starting VS Code

* Error

```
/Users/yusuke.ono/.pyenv/shims/python: line 21: /usr/local/Cellar/pyenv/1.2.22/libexec/pyenv: No such file or directory
/usr/local/bin/code: line 10: ./MacOS/Electron: No such file or directory
```

* This can be solved by running the following command.

```
$ pyenv rehash
```

## How to use the sips command

### PNG image profile check

```
$ find ~/Desktop -type f -name '*.png' -print0 | xargs -0 sips -g all
```

## How to use the Snap Camera on Microsoft Teams Mac OS client

```
#  (only if you haven't already)
$ xcode-select --install

$ sudo codesign --remove-signature "/Applications/Microsoft Teams.app"
$ sudo codesign --remove-signature "/Applications/Microsoft Teams.app/Contents/Frameworks/Microsoft Teams Helper.app"
$ sudo codesign --remove-signature "/Applications/Microsoft Teams.app/Contents/Frameworks/Microsoft Teams Helper (GPU).app"
$ sudo codesign --remove-signature "/Applications/Microsoft Teams.app/Contents/Frameworks/Microsoft Teams Helper (Plugin).app"
$ sudo codesign --remove-signature "/Applications/Microsoft Teams.app/Contents/Frameworks/Microsoft Teams Helper (Renderer).app"
```

cf. https://answers.microsoft.com/en-us/msteams/forum/all/microsoft-teams-mac-os-client-is-not-recognizing/d9e863be-d9a4-4d03-a4b8-1b5c7df58828?auth=1&page=13
