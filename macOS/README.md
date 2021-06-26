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
  - [Unzip fail when zip contains cjk char on macOS](#unzip-fail-when-zip-contains-cjk-char-on-macos)
  - [How to diff over ssh](#how-to-diff-over-ssh)
  - [How to check the character encoding with the file command](#how-to-check-the-character-encoding-with-the-file-command)
  - [How to count the number of columns in a TSV/CSV](#how-to-count-the-number-of-columns-in-a-tsvcsv)
  - [How to sort the results of the du command](#how-to-sort-the-results-of-the-du-command)
  - [How to check the expiration date of a SSL server certificate.](#how-to-check-the-expiration-date-of-a-ssl-server-certificate)
  - [How to get a list of files that have been changed between the last released revision and the latest revision in a subversion.](#how-to-get-a-list-of-files-that-have-been-changed-between-the-last-released-revision-and-the-latest-revision-in-a-subversion)
- [How to zoom on macOS](#how-to-zoom-on-macos)

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

## Unzip fail when zip contains cjk char on macOS

```
$  ditto -V -x -k --sequesterRsrc --rsrc FILENAME.ZIP DESTINATIONDIRECTORY
```

cf. https://github.com/CocoaPods/CocoaPods/issues/7711#issuecomment-386942543

## How to diff over ssh

```
$ ssh [.SSH_CONFIG_HOST] 'cat REMOTEFILEPATH' | diff - LOCALFILEPATH
$ diff <(ssh [.SSH_CONFIG_HOST] 'cat REMOTEFILEPATH') LOCALFILEPATH
```

## How to check the character encoding with the file command

```
$ file --mime hoge.php
```

## How to count the number of columns in a TSV/CSV

```
$ cat hoge.txt | awk -F '\t' '{print NF}'
$ cat hoge.txt | awk -F ','  '{print NF}'
```

## How to sort the results of the du command

```
$ du --max-depth=1 -h | sort -hr
```

## How to check the expiration date of a SSL server certificate.

```
$ openssl s_client -connect example.com:443 | openssl x509 -noout -enddate
```

## How to get a list of files that have been changed between the last released revision and the latest revision in a subversion.

```
$ svn diff --summarize --revision [revision_number]:head [path]
```

# How to zoom on macOS

```
option + command + 8
option + command + ^
option + command + -
```
