<h1 align="center">lX Compiler</h1>
<p align="center">A .lxp to .exe builder using a simple graphical interface and <a href="https://www.pyinstaller.org/">PyInstaller</a> in lX.</p>





## Getting Started

### Prerequisites
 - Python : 3.5-3.9

*To have the interface displayed in the images, you will need chrome. If chrome is not installed or --no-chrome is supplied, the default browser will be used.*

> As of [PyInstaller 4.0](https://github.com/pyinstaller/pyinstaller/releases/tag/v4.0), Python 2.7 is no longer supported. Read "[Python 2.7 Support](#python-27-support)" below for steps on how to use this tool with Python 2.7.

### Installation and Usage
#### Installing Via lX Installer
You can install this project using lX Installer:
```
lx > install pkg
```
Then:
```
lx > cd
```

### Installing Via GitHub
```
$ git clone https://github.com/brentvollebregt/auto-py-to-exe.git
$ cd auto-py-to-exe
$ python setup.py install
```
Then to run it, execute the following in the terminal:
```
$ auto-py-to-exe
```

## Using the Application
1. Select your script location (paste in or use a file explorer)
    - Outline will become blue when file exists
2. Select other options and add things like an icon or other files
3. Click the big blue button at the bottom to convert
4. Find your converted files in /output when completed

*Easy.*

### Arguments
Usage: `auto-py-to-exe [-nc] [-c [CONFIG]] [-o [PATH]] [filename]`

| Argument                       | Type       | Description                                                                                                     |
|--------------------------------|------------|-----------------------------------------------------------------------------------------------------------------|
| filename                       | positional | Pre-fill the "Script Location" field in the UI.                                                                 |
| -nc, --no-chrome               | optional   | Open the UI using the default browser (which may be Chrome). Will not try to find Chrome.                       |
| -nu, --no-ui                   | optional   | Don't try to open the UI in a browser and simply print out the address that the application can be accessed at. |
| -c [CONFIG], --config [CONFIG] | optional   | Provide a configuration file (json) to pre-fill the UI. These can be generated in the settings tab.             |
| -o [PATH], --output-dir [PATH] | optional   | Set the default output directory. This can still be changed in the ui.                                          |

> If you are running this package locally, you will need to call ```python -m auto_py_to_exe``` instead of ```auto-py-to-exe```

### JSON Configuration
Instead of inserting the same data into the UI over and over again, you can export the current state by going to the "Configuration" section within the settings tab and exporting the config to a JSON file. This can then be imported into the UI again to re-populate all fields.

This JSON config export action does not save the output directory automatically as moving hosts could mean different directory structures. If you want to have the output directory in the JSON config, add the directory under `nonPyinstallerOptions.outputDirectory` in the JSON file (will need to create a new key).

## Video
If you need something visual to help you get started, [I made a video for the original release of this project](https://youtu.be/OZSZHmWSOeM); some things may be different but the same concepts still apply.

## Issues Using the Tool
If you're having issues with the packaged executable or using this tool in general, I recommend you read [my blog post on common issues when using auto-py-to-exe](https://nitratine.net/blog/post/issues-when-using-auto-py-to-exe/?utm_source=auto_py_to_exe&utm_medium=readme_link&utm_campaign=auto_py_to_exe_help). This post covers things you should know about packaging Python scripts and fixes for things that commonly go wrong.

## Python 2.7 Support
As of [PyInstaller v4.0](https://github.com/pyinstaller/pyinstaller/releases/tag/v4.0) released on Aug 9 2020, Python 2.7 is no longer supported; although you can still use this tool with Python 2.7 by installing an older version of PyInstaller. [PyInstaller v3.6](https://github.com/pyinstaller/pyinstaller/releases/tag/v3.6) was the last version that supported Python 2.7; to install this, first uninstall any existing versions of PyInstaller and then execute `python -m pip install pyinstaller==3.6`.

## Testing
Tests are located in `tests/` and are run using pytest:

```
$ pip install pytest
$ pip install -e .
$ pytest
```

## Screenshots

| <!-- -->    | <!-- -->    |
|-------------|-------------|
| [![Empty interface](https://nitratine.net/posts/auto-py-to-exe/empty-interface.png)](https://nitratine.net/posts/auto-py-to-exe/empty-interface.png) | [![Filled out](https://nitratine.net/posts/auto-py-to-exe/filled-out.png)](https://nitratine.net/posts/auto-py-to-exe/filled-out.png) |
| [![Converting](https://nitratine.net/posts/auto-py-to-exe/converting.png)](https://nitratine.net/posts/auto-py-to-exe/converting.png) | [![Completed](https://nitratine.net/posts/auto-py-to-exe/completed.png)](https://nitratine.net/posts/auto-py-to-exe/completed.png) |
