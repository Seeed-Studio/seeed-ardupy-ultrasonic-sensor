# Seeed ArduPy Ultrasonic Sensor [![Build Status](https://api.travis-ci.com/Seeed-Studio/seeed-ardupy-ultrasonic-sensor.svg?branch=master)](https://travis-ci.com/github/Seeed-Studio/seeed-ardupy-ultrasonic-sensor)

## Introduction

This Grove - Ultrasonic ranger is a non-contact distance measurement module which works at 40KHz. When we provide a pulse trigger signal with more than 10uS through singal pin, the Grove_Ultrasonic_Ranger will issue 8 cycles of 40kHz cycle level and detect the echo. The pulse width of the echo signal is proportional to the measured distance. Here is the formula: Distance = echo signal high time * Sound speed (340M/S)/2. Grove_Ultrasonic_Ranger's trig and echo singal share 1 SIG pin.

You can get more information in here [Grove_Ultrasonic_Ranger](https://github.com/Seeed-Studio/Grove_Ultrasonic_Ranger).

<img src="https://statics3.seeedstudio.com/seeed/img/2016-09/kIyY21sbC6ct7JYzCWf1mAPs.jpg" width="300"><img src="https://statics3.seeedstudio.com/seeed/img/2016-09/8GLUR8JbFtrFzzISisBuVDey.jpg" width="300">
## How to binding with ArduPy
- Install [AIP](https://github.com/Seeed-Studio/ardupy-aip)
- Build firmware with Seeed ArduPy ultrasonic Sensor
```shell
aip install Seeed-Studio/seeed-ardupy-ultrasonic-sensor
aip build
```
- Flash new firmware to you ArduPy board
```shell
aip flash
#aip flash [path of the new firmware]
```
For more examples of using AIP, please refer to [AIP](https://github.com/Seeed-Studio/ardupy-aip).

## Usage

```python
from arduino import grove_ultra_ranger
import time

ur = grove_ultra_ranger(board.D0)

while True:
    #error:
    #    print ("The distance to obstacles in front is:", ur.cm, "cm", ur.inch, "inches")
    #    the second value (ur.inch) will got zero.
    #reason:
    #    there is a need for some time delay between two adjacent data acquisition
    print ("The distance to obstacles in front is:", ur.cm, " cm")
    #print ("The distance to obstacles in front is:", ur.inch, " inches")
    time.sleep(1)
```

## API Reference

- **cm** : Get distance in centimeters
```python
print(ur.cm)
```

- **inch**: Get distance in inches
```python
 print(ur.inch)
```
----

This software is written by seeed studio<br>
and is licensed under [The MIT License](http://opensource.org/licenses/mit-license.php). Check License.txt for more information.<br>

Contributing to this software is warmly welcomed. You can do this basically by<br>
[forking](https://help.github.com/articles/fork-a-repo), committing modifications and then [pulling requests](https://help.github.com/articles/using-pull-requests) (follow the links above<br>
for operating guide). Adding change log and your contact into file header is encouraged.<br>
Thanks for your contribution.

Seeed Studio is an open hardware facilitation company based in Shenzhen, China. <br>
Benefiting from local manufacture power and convenient global logistic system, <br>
we integrate resources to serve new era of innovation. Seeed also works with <br>
global distributors and partners to push open hardware movement.<br>


[![Analytics](https://ga-beacon.appspot.com/UA-46589105-3/Grove_LED_Bar)](https://github.com/igrigorik/ga-beacon)
