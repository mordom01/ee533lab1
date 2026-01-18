# ee533lab1

VM Server: 10.0.2.5
VM Client: 10.0.2.3

# EE 533 Lab 1: Socket Programming Setup

**Name:** Michael Qim  
**Date:** January 17 2026  
**Lab:** Network Processor Design - Lab 1

## Objective
Set up virtual machine environment and test basic TCP socket communication between client and server.

## Environment Setup
- **Host:** MacBook (ARM processor)
- **Hypervisor:** VirtualBox 7
- **OS:** Ubuntu 24.04 LTS
- **Network Type:** NAT Network (LabNetwork)
- **Server VM IP:** 10.0.2.5
- **Client VM IP:** 10.0.2.3

## Files
- `server.c` - TCP server that listens on specified port
- `client.c` - TCP client that connects to server and sends message

## Compilation
```bash
gcc server.c -o server
gcc client.c -o client
```

## Execution

**Server:**
```bash
./server 51717
```

**Client:**
```bash
./client 10.0.2.5 51717
```

## Test Results
- Successfully established TCP connection between VMs
- Client sent message: "Hello from client"
- Server received and displayed message
- Server sent acknowledgment: "I got your message"
- Client received and displayed acknowledgment

## Notes
- Added missing header files (stdlib.h, string.h, strings.h, unistd.h) to compile on Ubuntu 24
- Used port 51717 for testing
- Both programs terminate after single message exchange
