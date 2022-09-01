# MacBook Touch Bar Quick Actions

This repository holds my favorite quick actions for file handling.

1. `dateCreated_.workflow`: Prepends **the file's creation date** to the file name.
2. `dateToday_.workflow`: Prepends **today's** date to the file name.

These dates are added [ISO8601](https://en.wikipedia.org/wiki/ISO_8601)-compliant (YYYY-MM-DD).

![](img/ISO8601_date.png)
https://www.reddit.com/r/ProgrammerHumor/comments/uptfy9/dating_a_programmer/?utm_source=share&utm_medium=web2x&context=3

Quick actions are special types of macOS "Automator workflows". Somewhat intuitive to design and customize via the "Automator" app.

## Add quick actions to your touch bar

1. Open the System Preferences "Keyboard"
   1. Via clicking or 
   2. Via terminal: `open -b com.apple.systempreferences /System/Library/PreferencePanes/Keyboard.prefPane`

1. Check the box "Show Control Strip"

2. Open the menu to "Customize Control Strip"

![](img/keyboardPref.drawio.svg)

4. Add "Quick Actions" to your touch bar by drag-and-drop.

![](img/customizeControl.drawio.svg)

## Copy quick actions to your system

1. Navigate to  `~/Library/Services`
   1. Via terminal: `open ~/Library/Services` or 
   2. Via finder, go to (<kbd> &#8984; </kbd>+<kbd>&#8679;</kbd>+<kbd> G </kbd>), copy-paste `~/Library/Services`, enter.

2. Copy the quick actions from this repository to the folder `~/Library/Services`

3. The new quick actions should now appear in your "Extensions" System Preferences, open them
      1. via clicking there or ... 
      2. via terminal: `open -b com.apple.systempreferences /System/Library/PreferencePanes/Extensions.prefPane`

![](img/extensionPref.png)

## Test

1. Open a finder window and select one or multiple files or folders
2. Click the quick actions menu in your touch bar

![](img/TouchBar.png)

3. and use one of the Quick Actions on the files.

![](img/TouchBarQuickActions.png)

## Warning

- quick actions on files / folders will be done twice without a warning
  - already have a prepended date? => double date: 2022-09-01_2022-09-01_fileName.txt

## Customize

In the `~/Library/Services` double-click one of the workflows to open it in "Automator" and adapt it to your needs or create a new one.

## Source

Adapted from: https://www.idownloadblog.com/2020/01/07/run-quick-actions-touch-bar-mac-tutorial/


![](https://imgs.xkcd.com/comics/iso_8601_2x.png)
https://xkcd.com/1179



