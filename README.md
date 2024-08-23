# Laravel Herd Notes

## Introduction

This document serves as a collection of notes while I transition to using **Laravel Herd**. As a **TALL/VILT** developer, I primarily work on physical Linux servers, but I’m now exploring Laravel Herd and testing its capabilities.

## Directory Separators

Directory separators differ between **Windows** and **Linux** systems. If you've hard-coded any directory separators, such as `/` (forward slash) or `\` (backslash), as strings in your code, you should replace them with the `DIRECTORY_SEPARATOR` constant. This ensures compatibility across different operating systems.

### Example

**Incorrect:**
```php
$path = 'folder/subfolder/file.txt'; // This will work on Linux but not on Windows
$path = 'folder\\subfolder\\file.txt'; // This will work on Windows but not on Linux
$path = 'folder' . DIRECTORY_SEPARATOR . 'subfolder' . DIRECTORY_SEPARATOR . 'file.txt'; // This works on both Linux and Windows
```
By using DIRECTORY_SEPARATOR, your code will adapt to the correct directory separator for the operating system it’s running on.

You can now copy and paste this directly into your markdown file.
