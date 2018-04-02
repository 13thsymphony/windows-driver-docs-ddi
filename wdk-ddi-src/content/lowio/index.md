---
UID: NA:lowio
ms.assetid: 7ceab49f-fa99-3bc1-9f95-0357fe838006
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Lowio.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Lowio.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:----

# lowio.h header



lowio.h contains the following programming interfaces:





## Functions
| Title | Description |
| ---- |:---- |
| [RxLowIoCompletion](nf-lowio-rxlowiocompletion.md) | RxLowIoCompletion must be called by the network mini-redirector low I/O routines when they complete, if the low I/O routines have initially returned STATUS_PENDING. |
| [RxLowIoGetBufferAddress](nf-lowio-rxlowiogetbufferaddress.md) | RxLowIoGetBufferAddress returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure. |