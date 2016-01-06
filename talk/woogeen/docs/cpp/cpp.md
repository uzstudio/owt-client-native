The Intel CS for WebRTC Client Windows\* SDK
==================================
Introduction
------------
The Intel CS for WebRTC Client SDK for Windows provides the tools for developing Windows native WebRTC applications using C++ APIs. This document describes all the APIs available in the SDK and how to use them.

This SDK is interoperable with the Intel CS WebRTC Client SDK for JavaScript\*, iOS\* and Android\*.

Refer to the Release Notes for the latest information in the SDK release package, including features, bug fixes and known issues.

Supported Platforms
-------------------
The Intel CS for WebRTC Client SDK for Windows supports Windows 7 and later versions.

Getting Started
---------------
The release package includes two sample applications to get you started quickly with the SDK. The following three static libraries are provided in the SDK along with their respective headers:

TODO: Confirm it before release

- woogeen.lib - this library includes all the WebRTC features.
- sioclient.lib - this library includes Socket.IO C++ client without TLS features.
- sioclient_tls.lib - this library includes the Socket.IO C++ client with TLS features.

Socket.IO
---------
Socket.IO cpp client is an open source project host on [Github](https://github.com/socketio/socket.io-client-cpp).

The Socket.IO TLS feature is determined at compile time and cannot be switched at runtime. If you are using secure connections, link your application with sioclient_tls.lib; otherwise, link it with sioclient.lib.

The sioclient_tls.lib included in release package has been enhanced so it will verify server's certificate. If the server is using an invalid certificate, handshake will fail. You can also compile Socket.IO lib (v1.6.1) by yourself.

Customize Signaling Channel
-----------------------------
Signaling channel is an implementation to transmit signaling data for creating a WebRTC session. Signaling channel for P2P sessions can be customized by implementing `P2PSignalingChannelInterface`. We provides a default `P2PSocketSignalingChannel` in sample which works with PeerServer in the release package.

`PeerClient` implements `P2PSignalingChannelInterfaceObserver` and will be registered into signaling channel, so you can invoke its methods to notify `PeerClient` during your customized signaling channel implementation when a new message is coming or connection is lost.

Known Issues
------------
Here is a list of known issues:

- Conference recording is not supported.
- Subscribe streams with audio/video only option is not supported.
- Get connection stats is not supported.
- Bitrate control is not supported. It may costs up to 2Mbps per connection.
- If you create multiple `LocalCameraStream`s with different resolutions, previous streams will be black.

Video Codecs
------------
Both VP8 and H.264 are supported.

Publish Streams with Encoded Frames
------------
TODO:

Intel CS for WebRTC Websites
----------------------------
[Home page](http://webrtc.intel.com)

[Forum](https://software.intel.com/en-us/forums/intel-collaboration-suite-for-webrtc)


<i>Note: \*Other names and brands may be claimed as the property of others.</i>