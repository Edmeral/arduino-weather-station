I created this project to experiment with using an Arduino board and a Raspberry Pi together, it's basically a simple weather station with live updates accessible from the Internet. Demo [here](http://weather.aissam.me).

## How it works
The Arduino gets the weather information from the [DHT11 sensor](http://www.adafruit.com/product/386), parses that information then sends it to Raspberry Pi (or any computer) via serial port (usb), the Pi gets that information and sends it to the [sparkfun API](https://data.sparkfun.com/streams/xROLbJzAlMcjwlN5dolp) to be stored there. The `master` branch contains the code that does this: the arduino folder is destined to be sent to the Arduino board, while server.js is to be run on the the Raspberry Pi.

The `alternative` branch contains another way to do this, by using only the Raspberry Pi connected directly to the DHT11 sensor without using the Arduino board. 

The `gh-pages` branch contains the code for the [demo](http://weather.aissam.me), basically it's an html page with a js script that fetch the latest data entries from the [sparkfun API](https://data.sparkfun.com/streams/xROLbJzAlMcjwlN5dolp), and updates the page accordingly.
