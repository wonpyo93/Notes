# NSD Manager

### NsdManager: MDNS Service를 검색하거나 Service를 생성하는 기능을 제공하는 구글 API이며, 같은 네트워크에 존재하는 LG Wi-Fi Speaker를 찾을 수 있는 Class
### The Network Service Discovery Manager class provides the API to discover services on a network.
### The API currently supports DNS based service discovery and discovery is currently limited to a local network over Multicast DNS(MDNS).
### The API is asynchronous, and responses to requests from an application are on listener callbacks on a separate internal thread.

![image](https://user-images.githubusercontent.com/49303504/152706481-429b6b20-6f39-4172-8105-7574ee527657.png)

### An application that needs to advertise itself over a network for other applications to discover it can do so with a call to registerService().
### If example is a http based application that can provide HTML data to peer services, it can register a name ‘Example’ with servie type ‘_http._tcp’. 그래서 사운드바의 경우, service type을 ‘_lg-smart-device._tcp’로 지정하였음.

#### A successful registration is notified with RegistrationListener#onServiceRegistered 
#### and a failure register is notified over RegistrationListener#onRegistrationFailed.

### A peer application looking for http services can initiate a discovery for ‘_http._tcp’ with a call to discoverService(). 

#### A service found is notified with a callback to DiscoveryListener#onServiceFound and a service lost is notified on DiscoveryListener#onServiceLost.

### Once the peer application discovers the ‘Example’ http service, and either needs to read the attributes of the service or wants to receive data from the ‘example’ application, it can initiate a resolve with resolveService() to resolve the attributes, host, and port details.

#### A successful resolve is notified on ResolveListener#onServiceResolved and a failure is notified on ResolveListener#onResolveFailed. 
