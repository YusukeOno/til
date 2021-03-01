# macOS Tips

- [macOS Tips](#macos-tips)
  - [How to rename a screenshot file in macOS](#how-to-rename-a-screenshot-file-in-macos)
  - [How to use Safari's PiP for YouTube](#how-to-use-safaris-pip-for-youtube)
  - [How to merge files horizontally](#how-to-merge-files-horizontally)
  - [How to input logo mark the Apple .](#how-to-input-logo-mark-the-apple-)
  - [How to deal with errors when starting VS Code](#how-to-deal-with-errors-when-starting-vs-code)
  - [How to use the sips command](#how-to-use-the-sips-command)
    - [PNG image profile check](#png-image-profile-check)

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
