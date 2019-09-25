# Change Log

## Current Version

v2.0.8

- StartAsync() method for client and server

## Previous Versions

v2.0.x

- Changed .NET Framework minimum requirement to 4.6.1 to support use of ```TcpClient.Dispose```
- Better disconnect handling and support (thank you to @mikkleini)
- Async Task-based callbacks
- Configurable connect timeout in WatsonTcpClient
- Clients can now connect via SSL without a certificate
- Big thanks to @MrMikeJJ for his extensive commits and pull requests
- Bugfix for graceful disconnect through dispose (thank you @mikkleini!)
 
v1.3.x
- Numerous fixes to authentication using preshared keys
- Authentication callbacks in the client to handle authentication events
  - ```AuthenticationRequested``` - authentication requested by the server, return the preshared key string (16 bytes)
  - ```AuthenticationSucceeded``` - authentication has succeeded, return true
  - ```AuthenticationFailure``` - authentication has failed, return true
- Support for sending and receiving larger messages by using streams instead of byte arrays
- Refer to ```TestServerStream``` and ```TestClientStream``` for a reference implementation.  You must set ```client.ReadDataStream = false``` and ```server.ReadDataStream = false``` and use the ```StreamReceived``` callback instead of ```MessageReceived```

v1.2.x
- Breaking changes for assigning callbacks, various server/client class variables, and starting them
- Consolidated SSL and non-SSL clients and servers into single classes for each
- Retargeted test projects to both .NET Core and .NET Framework
- Added more extensible framing support to later carry more metadata as needed
- Added authentication via pre-shared key (set Server.PresharedKey class variable, and use Client.Authenticate() method)

v1.1.x
- Re-targeted to both .NET Core 2.0 and .NET Framework 4.5.2
- Various bugfixes

v1.0.x
- Initial release
- Async support and IDisposable support
- IP filtering/permitted IP addresses support
- Improved disconnect detection
- SSL support