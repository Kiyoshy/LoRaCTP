# Pi Wave Compressor

The code in this repository enables you to create a graphical interface for recording audio files and compressing them into files that are 10x smaller without compromising audio quality.

Use case details can be found in this journal:
> K. Nakamura, D. Hernández, J. M. Cecilia, P. Manzoni, M. Zennaro, J. -C. Cano and C. T. Calafate, 
> "LADEA: A Software Infrastructure for Audio Delivery and Analytics," 
> Mobile Networks and Applications (MONET), Volume 26, Oct 2021, pp. 2048-2054, 
> [doi: 10.1007/s11036-021-01747-z.](https://doi.org/10.1007/s11036-021-01747-z)


## Getting started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes in your Raspberry.


### Technical details

* [Raspberry Pi 3 B+](https://www.raspberrypi.com/products/raspberry-pi-3-model-b-plus/) the final revision of the third-generation single-board computer.

* [Raspberry Pi OS Desktop](https://www.raspberrypi.com/software/operating-systems/)

* [3.5'' RPi Display](http://www.lcdwiki.com/3.5inch_RPi_Display)

To configure the display and drivers, proceed as follows:
```
$ sudo rm -rf LCD-show
$ git clone https://github.com/goodtft/LCD-show.git
$ chmod -R 755 LCD-show
$ cd LCD-show/
$ sudo ./LCD35-show
```
For more information you can check [documentation](http://www.lcdwiki.com/3.5inch_RPi_Display). 


### Prerequisites

This is the basic information required to set up a suitable development environment for a Raspberry Pi 3 B+ device.

You first need to have Python 3 and Pip 3 installed in your device. Check here for the proper instructions and code:
```
https://www.python.org/download/releases/3.0/

$ sudo apt install python3
$ sudo apt install python3-pip
```

Additionally, you need to configure the audio output of your Raspberry, depending on the type of headphones you are going to use.
```
$ sudo raspi-config
```
Go to <<Advance Options/Audio/Force 3.5mm Jack>> in case you are going to use headphones with that input/output.


### Required libraries and packages

* [Pyaudio](https://pypi.org/project/PyAudio/)

* [Pydub](https://pypi.org/project/pydub/)

* [Sounddevice](https://python-sounddevice.readthedocs.io/en/0.4.6/)

* [FFmpeg](https://ffmpeg.org/)

* [Tkinter](https://docs.python.org/3/library/tkinter.html)

* [Matplotlib](https://matplotlib.org/)

```
$ sudo pip install pyaudio
$ sudo pip install pydub
$ sudo pip install sounddevice
$ sudo apt-get install ffmpeg libav-tools
$ sudo apt-get install libasound-dev portaudio19-dev libportaudio2 libportaudiocpp0
$ sudo apt install python3-tk
$ sudo python3 -m pip install -U matplotlib
```


### Running

Now you can download and install the project in your devices.

First download the .ZIP, extract it in your device.

Open the terminal at the project location and run.
```
$ sudo python3 touch_scr.py
```


### Files

The code in this folder is written in Python 3 and tested on:

Files contained:

* The `Img` folder contains all the images required by the graphical interface, as well as the photos of previously registered users.

* The `touch_scr.py` file is responsible for generating the graphical interface and performing the user interaction actions.

* The `rec.py` file is tasked with generating, processing, and compressing the audio files.


## Experimental

The interface is designed to be highly user-friendly, with the utilization of icons that dynamically enable/disable to effectively guide the user through the entire process of recording an audio message.

![](demo.png)

Audio messages generated on the Raspberry can be transmitted using LoRa devices with the help of the [LoRaCTP](https://github.com/Kiyoshy/LoRaCTP) protocol.

![](prototype.jpg)


## Authors

* **Kiyoshy Nakamura**
* **Pietro Manzoni**


## License

This project is licensed under the GNU GPLv3 - see the [LICENSE](LICENSE) file for details.