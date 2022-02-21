# Jmdns

### Jmdns는 multi-cast DNS의 Java Implementation이다. Apple 사의 Bonjour도 Jmdns 기법을 활용하고 있다.
### Jmdns 공식 사이트에서는 이렇게 소개하고 있다.
> The Zeroconf working group is working towards zero configuration IP networking.
> Multi-cast DNS and DNS service discovery provide a convient ways for devices and services to register themselves,
> and to discover other network-based services without relying on centrally administered services.
이건 Jmdns보다는 zeroconf의 mdns 기법 전체적으로 해당하는 말.
> Java as a language is not appropriate for low-level network configuration, but it is very useful for service registration and discovery.
> JmDNS provides easy-to-use pure-Java mDNS implementation that runs on most JDK1.6 compatible VMs.

이미 NSDManager라는 것을 알게 된 시점에서, Jmdns를 굳이 왜 쓰는지 알아보자.

### JMDNS vs NSD
> NSDManager는 JMDNS보다 훨씬 더 빠르다.
> 그런데 NSDManager의 경우, resolved 단계에서 fail이 뜰 수가 있는데, 이게 한번이라도 fail이 뜨면
> 계속 fail이 뜨게 된다.(필자만 그런 것인지...)
> 하지만 JMDNS는 절대 fail이 뜨지 않는다.
> 하지만 무의미한 IP도 다 긁어 온다는 단점이 존재한다.
> 
##### (출처: [1](http://jmdns.sourceforge.net/))

