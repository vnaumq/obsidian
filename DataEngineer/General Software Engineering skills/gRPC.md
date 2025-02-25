[[General Software Engineering skills]]

## Why gRPC?

gRPC is an RPC (Remote Procedure Call) framework initially developed by Google, currently open-sourced. gRPC is based on **HTTP2** and uses **protocol buffers** for message exchange that makes it quite convenient and performant.

Protocol Buffers offer the following added advantages:

- Faster serialization and deserialization
- Smaller message size
- Strongly-typed and schema-based contracts
- Language-neutral and cross-platform support

## Architecture of gRPC
![[grpc.jpeg]]

This shows how gRPC uses HTTP/2 as the transport layer and Protocol Buffers as the serialization format to enable efficient and reliable communication between distributed systems and microservices.

The workflow consists of four main layers: the network layer, the client layer, the server layer, and the protocol buffers layer. The network layer represents the HTTP/2 protocol that gRPC uses to send and receive messages over the internet.

The client layer and the server layer represent the applications that use gRPC to communicate with each other. The protocol buffers layer represents the data format that gRPC uses to encode and decode messages.

The flow involves several steps, such as calling, serializing, sending, receiving, deserializing, handling, and returning gRPC methods and messages using generated stubs and services.