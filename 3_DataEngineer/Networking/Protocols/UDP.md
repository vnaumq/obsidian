[[Protocols]]

## What is the User Datagram Protocol (UDP/IP)?

The User Datagram Protocol, or UDP, is a communication protocol used across the Internet for especially time-sensitive transmissions such as [video playback](https://www.cloudflare.com/learning/video/what-is-streaming/) or [DNS](https://www.cloudflare.com/learning/dns/what-is-dns/)lookups. It speeds up communications by not formally establishing a connection before data is transferred. This allows data to be transferred very quickly, but it can also cause [packets](https://www.cloudflare.com/learning/network-layer/what-is-a-packet/) to become lost in transit — and create opportunities for exploitation in the form of [DDoS attacks](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/).

## How does UDP work?

Like all [networking protocols](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/), UDP is a standardized method for transferring data between two computers in a network. Compared to other protocols, UDP accomplishes this process in a simple fashion: it sends packets (units of data transmission) directly to a target computer, without establishing a connection first, indicating the order of said packets, or checking whether they arrived as intended. (UDP packets are referred to as ‘datagrams’.)

#### TCP vs. UDP

UDP is faster but less reliable than [TCP](https://www.cloudflare.com/learning/ddos/glossary/tcp-ip/), another common transport protocol. In a TCP communication, the two computers begin by establishing a connection via an automated process called a ‘handshake.’ Only once this handshake has been completed will one computer actually transfer data packets to the other.

UDP communications do not go through this process. Instead, one computer can simply begin sending data to the other:
![[tcp-vs-udp.svg]]

In addition, TCP communications indicate the order in which data packets should be received and confirm that packets arrive as intended. If a packet does not arrive — e.g. due to congestion in intermediary networks — TCP requires that it be re-sent. UDP communications do not include any of this functionality.

These differences create some advantages. Because UDP does not require a ‘handshake’ or check whether data arrives properly, it is able to transfer data much faster than TCP.

However, this speed creates tradeoffs. If a UDP datagram is lost in transit, it will not be re-sent. As a result, applications that use UDP must be able to tolerate errors, loss, and duplication.

(Technically, such packet loss is less a flaw in UDP than a consequence of how the Internet is built. Most network [routers](https://www.cloudflare.com/learning/network-layer/what-is-a-router/) do not perform packet ordering and arrival confirmation by design, because doing so would require an unfeasible amount of additional memory. TCP is a way of filling this gap when an application requires it.)

