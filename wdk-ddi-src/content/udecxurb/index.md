---
UID: NA:udecxurb
ms.assetid: 6cb5d20a-c66a-3e85-8ef2-8930ca44e63a
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Udecxurb.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Udecxurb.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:----

# udecxurb.h header



udecxurb.h contains the following programming interfaces:





## Functions
| Title | Description |
| ---- |:---- |
| [UdecxUrbComplete](nf-udecxurb-udecxurbcomplete.md) | Completes the URB request with a USB-specific completion status code. |
| [UdecxUrbCompleteWithNtStatus](nf-udecxurb-udecxurbcompletewithntstatus.md) | Completes the URB request with an NTSTATUS code. |
| [UdecxUrbRetrieveBuffer](nf-udecxurb-udecxurbretrievebuffer.md) | Retrieves the transfer buffer of an URB from the specified framework request object sent to the endpoint queue. |
| [UdecxUrbRetrieveControlSetupPacket](nf-udecxurb-udecxurbretrievecontrolsetuppacket.md) | Retrieves a USB control setup packet from a specified framework request object. |
| [UdecxUrbSetBytesCompleted](nf-udecxurb-udecxurbsetbytescompleted.md) | Sets the number of bytes transferred for the URB contained within a framework request object. |