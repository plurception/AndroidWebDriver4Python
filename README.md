# Introduction

_Author: Sean Wang xiao.wang@symbio.com_

AndroidWebDriver4Python is an addon to [Selenium Python Client Driver](http://pypi.python.org/pypi/selenium)

This addon supports multiple real devices simultaneously from release 1.1, but not supports emulators. I have not figured out yet.


As I could not find Android WebDriver implementation in it,and I really like Python as opposed to Java. So I want to implement one.
I know that I am a newbie, I do not expect to commit in the Selenium project.


More infomation about *Selenium*, plz check http://code.google.com/p/selenium/

# Installing

To install this AndroidDriver for Python, you need:

1. download AndroidWebDriver4Python using command: 

```
$ git clone git://github.com/truebit/AndroidWebDriver4Python.git
```

2. download and extract [Selenium Python client](http://pypi.python.org/pypi/selenium#downloads)
3. copy the entire `py` folder under AndroidWebDriver4Python to merge the
same one in root directory of AndroidDriver for Python
4. back to the root directory of Selenium Python Client, to install this modified version using command:

```
$ python setup.py install
```

Here you have installed this AndroidWebDriver4Python add-on.
There are some prerequisites to use AndroidWebDriver4Python.

* [Install Android SDK](http://developer.android.com/sdk/installing.html) and set its `tools` and `platform-tools` in your PATH
* Install Android server side application [android-server-2.x.x.apk](http://code.google.com/p/selenium/downloads/list) on your device
* enable `USB Debugging` in your device and disable autolock, which normally could found from `Home>Settings>Applications>Development>USB debugging`

* connect USB cable between device and PC, install adb drivers

# Example
```python
from selenium import webdriver

# if only one device connected, you do not need to specifiy the serial id.
# exmaple driver=webdriver.Android()
driver1= webdriver.Android('HT1234567')
driver2=webdriver.Android('091012345601E00D')
driver1.get("http://www.symbio.com")
driver2.get("http://www.google.com.hk")
driver1.quit()
driver2.quit()
```

If you want more detailed example, plz check [example.py](AndroidWebDriver4Python/blob/master/example/example.py)

# Documentation

The latest [Selenium Python Bindings documentation](http://readthedocs.org/docs/selenium-python/en/latest)

# Use The Source Luke!

As this Android Driver I implemented is herited from [webdriver.py](http://code.google.com/p/selenium/source/browse/trunk/py/selenium/webdriver/remote/webdriver.py), so plz see its source code to use Android driver just like other WebDriver.
