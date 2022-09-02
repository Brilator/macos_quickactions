# MacBook Touch Bar Quick Actions

This repository holds my favorite quick actions for file handling.

![TouchBar](img/TouchBarQuickActions.png)

By just a click (finger-tip) in your touch bar, ...
   - ... `dateCreated_.workflow` prepends **the file's creation date** to the file name.
   - ... `dateToday_.workflow` prepends **today's** date to the file name.
   - ... `docx2PDF.workflow` **generates a PDF** from a selected `*.docx` file [(see additional notes)](#docx2pdf)

These dates are added [ISO8601](https://en.wikipedia.org/wiki/ISO_8601)-compliant (YYYY-MM-DD).

<figure>
  <img src="img/ISO8601_datingProgrammer.png" style="width:80%">
  <figcaption align = "left"><p style="color:grey;font-size:8px;">https://www.reddit.com/r/ProgrammerHumor/comments/uptfy9/dating_a_programmer/</p></figcaption>
</figure>

Quick actions are special types of macOS "Automator workflows". Somewhat intuitive to design and customize via the "Automator" app.

- [Add quick actions to your touch bar](#add-quick-actions-to-your-touch-bar)
- [Copy quick actions to your system](#copy-quick-actions-to-your-system)
- [Test](#test)
- [Warnings](#warnings)
  - [docx2PDF](#docx2pdf)
- [Customize](#customize)
- [Source](#source)


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

<img src="img/extensionPref.png" style="width:60%">

## Test

1. Open a finder window and select one or multiple files or folders
2. Click the quick actions menu in your touch bar

![](img/TouchBar.png)

3. and use one of the Quick Actions on your files.

![](img/TouchBarQuickActions.png)

## Warnings

Quick actions on files and folders will be done twice without a warning: already have a prepended date? => double date: 2022-09-01_2022-09-01_fileName.txt

### docx2PDF

> Note: This one is more complicated than the standard automator workflows.

1. It comes with dependencies you need to install.
2. It does not produce a perfect PDF like the one that MS Word would produce from your *.docx file. In particular, any (special) formatting, figures, tables, etc. will likely be off.

Still, for most quick "I want to convert those docx files to be able to easily share and read them on my other devices (tablet, smart phone, computer without word)", it does the job.

And, if it does not work, it will just not produce anything and probably display an error message. Your docx file will not be changed or deleted.

**Install dependencies:**

This tool requires [pandoc](https://pandoc.org/installing) and LaTeX (follow instructions on pandoc page) to be installed at exactly the default macOS locations. 

After installation, test wether the files are there: 

```bash
ls -l /usr/local/bin/pandoc
ls -l /Library/TeX/texbin/pdflatex
```

## Customize

In the `~/Library/Services` double-click one of the workflows to open it in "Automator" and adapt it to your needs or create a new one.

![](img/automator_quickAction.png)


## Source

Tutorial adapted from: https://www.idownloadblog.com/2020/01/07/run-quick-actions-touch-bar-mac-tutorial/

<figure>
  <img src="https://imgs.xkcd.com/comics/iso_8601_2x.png" style="width:80%">
  <figcaption align = "left"><p style="color:grey;font-size:8px;">https://xkcd.com/1179</p></figcaption>
</figure>