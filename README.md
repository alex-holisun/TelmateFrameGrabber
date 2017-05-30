#TelmateFrameGrabber

##Introduction:

This module implements a Kurento endpoint frames grabber.

The module uses the Kurento OpenCV support and receive reference to an opencv[cv::mat](http://docs.opencv.org/3.1.0/d3/d63/classcv_1_1Mat.html)object 

containing the frame data and saves it to disk.

A instance module is created for each Kurento endpoint.

 
##Compiling:

All basic Kurento libraries are needed as mentioned in [How to Develop Kurento Modules](http://doc-kurento.readthedocs.io/en/stable/mastering/develop_kurento_modules.html)

Please make sure Boost C++ and OpenCV are installed

To build the Java bindings, Maven is needed. 

```
git clone TelmateFrameGrabber.git
```

```
cd TelmateFrameGrabber
mkdir build # a place to build the code in.
cmake -DCMAKE_INSTALL_PREFIX=/usr .. # TO create the c++ code
cmake .. -DGENERATE_JAVA_CLIENT_PROJECT=TRUE # To generate the Java bindings.
make
make install
```

To comilple the java bindings:
```
cd java 
mvn compile exec:java

```

##Public Methods:

#### void setSnapInterval(int snapInterval): 
Optional, Recommended, Sets the snapshot interval (in milliseconds). Defaults to 1000ms.


#### void setStoragePath(const std::string &path):
Optional, Recommended, Sets the storage path location. Defaults to /tmp.

#### void setWebRtcEpName(const std::string &epName):
Optional, Sets the endpoint name. Defaults to NULL.

#### int getSnapInterval():
Returns the current configured snapshot interval. 

#### std::string getStoragePath():
Returns the current configured snapshots path.


## Classes:

#### TelmateFrameGrabberImpl:
Kurento Plugin. This class is an interface between the Kurento plugin core and the actual plugin. 

#### TelmateFrameGrabberOpenCVImpl:
This Class implements the plugin, Interacts with TelmateFrameGrabberImpl.


## Authors:
Avi Saranga 

## License & Distribution:
MIT License

Copyright (c) 2017 Telmate, LLC

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.