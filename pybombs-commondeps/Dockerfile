FROM pybombs/pybombs-prefix:2.3.3
LABEL maintainer=martin@gnuradio.org

# This allows setting the makewidth temporarily to a higher value
ARG makewidth=2

RUN pybombs config makewidth $makewidth
# Now list all the dependencies that we want to ship in this container:
# (I use separate RUN commands so I can maybe have an easier time building)
RUN pybombs install boost doxygen
RUN pybombs install libtool autoconf automake
RUN pybombs install qwt5 sip lxml
RUN pybombs install pygtk pycairo pyqwt5 python-requests six mako numpy
RUN pybombs install gsl fftw
RUN pybombs install zeromq python-zmq
RUN pybombs install libusb alsa
RUN pybombs install cppunit liblog4cpp

# We set it back to safe value before we finish
RUN pybombs config makewidth 2
