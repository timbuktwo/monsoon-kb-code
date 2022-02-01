+++
title = "Git Commands"
date = "2022-01-30T03:51:14-07:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["git", "CLI"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

## git commands:

`init` - begins versioning and adds hidden git files in the path where it's run\
`status` - gives status of git files\
`add` - stages files\
`add .` - stages ALL files in the directory recursively\
`commit` - commits the files to the git changelog\
`push` - pushes the change to an upstream repo (Github)\
`rm -rf .git` - deletes git versioning and versioning guts for a directory\
`rm -r --cached myfolder` - removes directory from git but NOT local\
`config --global core.autocrlf true` - converts LF endings into CRLF when you check out code.