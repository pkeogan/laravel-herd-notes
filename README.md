# Laravel Herd Notes

## Introduction

This document serves as a collection of notes while I transition to using **Laravel Herd**. As a **TALL/VILT** developer, I primarily work on physical Linux servers, but I’m now exploring Laravel Herd and testing its capabilities.

## PHP Extensions

Herd does not come with all the PHP extensions by default. Since I work with code across various versions of PHP, from older to the latest, it's important to manage these extensions efficiently.

Let Herd install everything as usual.

I recommend using the following PowerShell module for managing PHP extensions:

To install it, run:
`Install-Module -Name PhpManager -Repository PSGallery -Force -Scope CurrentUser`

Since Herd has already installed PHP for you, you'll need to specify the `-Path` parameter when using this command, pointing to the PHP version you're using.

### Herd Default PHP Locations

- **PHP 8.2**: `C:\Users\[username]\.config\herd\bin\php82`
- **PHP 8.3**: `C:\Users\[username]\.config\herd\bin\php83`

### Install Imagick Extension

To install the Imagick extension for the specific PHP versions, use the following commands:

- **PHP 8.2**:  
  `Install-PhpExtension imagick -Path "C:\Users\[username]\.config\herd\bin\php82"`

- **PHP 8.3**:  
  `Install-PhpExtension imagick -Path "C:\Users\[username]\.config\herd\bin\php83"`




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
