external video provider branch
======
new object can be added to RTCConfiguration: 
*videoPacketRecorder 
*audioPacketRecorder 
*videoPacketReplay 	
*audioPacketReplay 	

Replayer objects can bypass the encoder to supply already encoded media flux to RTCRtpSender
Recorder objects provide a way to get raw encoded incoming media flux from RTCRtpReceiver


aiortc
======

|rtd| |pypi-v| |pypi-pyversions| |pypi-l| |travis| |codecov| |gitter|

.. |rtd| image:: https://readthedocs.org/projects/aiortc/badge/?version=latest
   :target: https://aiortc.readthedocs.io/

.. |pypi-v| image:: https://img.shields.io/pypi/v/aiortc.svg
    :target: https://pypi.python.org/pypi/aiortc

.. |pypi-pyversions| image:: https://img.shields.io/pypi/pyversions/aiortc.svg
    :target: https://pypi.python.org/pypi/aiortc

.. |pypi-l| image:: https://img.shields.io/pypi/l/aiortc.svg
    :target: https://pypi.python.org/pypi/aiortc

.. |travis| image:: https://img.shields.io/travis/jlaine/aiortc.svg
    :target: https://travis-ci.org/jlaine/aiortc

.. |codecov| image:: https://img.shields.io/codecov/c/github/jlaine/aiortc.svg
    :target: https://codecov.io/gh/jlaine/aiortc

.. |gitter| image:: https://img.shields.io/gitter/room/aiortc/Lobby.svg
    :target: https://gitter.im/aiortc/Lobby

What is ``aiortc``?
-------------------

``aiortc`` is a library for `Web Real-Time Communication (WebRTC)`_ and
`Object Real-Time Communication (ORTC)`_ in Python. It is built on top of
``asyncio``, Python's standard asynchronous I/O framework.

The API closely follows its Javascript counterpart while using pythonic
constructs:

- promises are replaced by coroutines
- events are emitted using ``pyee.EventEmitter``

To learn more about ``aiortc`` please `read the documentation`_.

.. _Web Real-Time Communication (WebRTC): https://webrtc.org/
.. _Object Real-Time Communication (ORTC): https://ortc.org/
.. _read the documentation: https://aiortc.readthedocs.io/en/latest/

Why should I use ``aiortc``?
----------------------------

The main WebRTC and ORTC implementations are either built into web browsers,
or come in the form of native code. While they are extensively battle tested,
their internals are complex and they do not provide Python bindings.
Furthermore they are tightly coupled to a media stack, making it hard to plug
in audio or video processing algorithms.

In contrast, the ``aiortc`` implementation is fairly simple and readable. As
such it is a good starting point for programmers wishing to understand how
WebRTC works or tinker with its internals. It is also easy to create innovative
products by leveraging the extensive modules available in the Python ecosystem.
For instance you can build a full server handling both signaling and data
channels or apply computer vision algorithms to video frames using OpenCV.

Furthermore, a lot of effort has gone into writing an extensive test suite for
the ``aiortc`` code to ensure best-in-class code quality.

Implementation status
---------------------

``aiortc`` allows you to exchange audio, video and data channels and
interoperability is regularly tested against both Chrome and Firefox. Here are
some of its features:

- SDP generation / parsing
- Interactive Connectivity Establishment, including half-trickle
- DTLS key and certificate generation
- DTLS handshake, encryption / decryption (for SCTP)
- SRTP keying, encryption and decryption for RTP and RTCP
- Pure Python SCTP implementation
- Data Channels
- Sending and receiving audio (Opus / PCMU / PCMA)
- Sending and receiving video (VP8 / H.264)
- Bundling audio / video / data channels
- RTCP reports, including NACK / PLI to recover from packet loss

Requirements
------------

In addition to aiortc's Python dependencies you need a couple of libraries
installed on your system for media codecs. FFmpeg 3.2 or greater is required.

On Debian/Ubuntu run:

.. code:: bash

    apt install libavdevice-dev libavfilter-dev libopus-dev libvpx-dev pkg-config

On OS X run:

.. code:: bash

    brew install ffmpeg opus libvpx pkg-config

License
-------

``aiortc`` is released under the `BSD license`_.

.. _BSD license: https://aiortc.readthedocs.io/en/latest/license.html
