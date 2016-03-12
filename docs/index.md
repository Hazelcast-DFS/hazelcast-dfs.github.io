# Hazelcast - Distributed-Filesystem

This is based on the [HEP - HZDFS](https://hazelcast.atlassian.net/wiki/display/COM/HEP+%23+-+Hazelcast+Distributed+File+System+Layer)

## Summary
HZDFS the Hazelcast Distributed Filesystem Layer is a filesystem with simple access rights management and the possibility to store files larger than 2GB (chunked) in Hazelcast.

## Goals
+ Chunking of big files
+ Access rights management
+ Directory Service
+ User management
+ Streaming support (micro batching?)
+ Navigating directory trees and files

+ Support for files larger than 2GB
+ Java 7 Path API support?
+ Java Input-/OutputStream API?
+ Java 7 (Async-)ByteChannel API?

## Non-Goals
The implementation is not supposed to be fully POSIX compatible
No operating system adapters are part of this HEP

## Motivation
It will allow to use memory-consumption based eviction policy in case when in-memory-format is OBJECT

## Success Metrics
Typical CRUD operations on files and directories are available, as well as necessary mechanisms are in place to store files bigger than 2GB (chunking) and path walking / searching is possible. Files also need to support reading in a streaming fashion.

## Description
HZDFS the Hazelcast Distributed Filesystem Layer is supposed to build a filesystem with access rights management. Files will be stored in chunks and distributed evenly over all nodes with a directory service and lookup system being part of the clustering system.
Testing
Typical amount of unit tests as well as integration testing and long running tests utilizing internal eviction strategies and underlying external resources.

