---
UID : NF:vmbuskernelmodeclientlibapi.VmbPacketRestore
title : VmbPacketRestore function
author : windows-driver-content
description : The VmbPacketRestore function restores packet from a buffer that contains saved packet context.
old-location : netvista\vmbpacketrestore.htm
old-project : netvista
ms.assetid : CE8BBFB7-FC6C-458B-89EC-355A6DD18399
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : VmbPacketRestore function [Network Drivers Starting with Windows Vista], VmbPacketRestore, netvista.vmbpacketrestore, vmbuskernelmodeclientlibapi/VmbPacketRestore
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : vmbuskernelmodeclientlibapi.h
req.include-header : VmbusKernelModeClientLibApi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 1.13
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product : Windows 10 or later.
---


# VmbPacketRestore function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketRestore</b> function restores packet from a buffer that contains saved packet
context.

## Syntax

````
NTSTATUS VmbPacketRestore(
  _In_ __drv_aliasesMem VMBPACKET     PacketObject,
  _In_ reads_bytes_(BufferSize) PVOID Buffer,
  _In_ ULONG                          BufferSize
);
````

## Parameters

`PacketObject`

This is a handle of a VMBus packet.

`Buffer`

Pointer to buffer that contains previously saved context.

`BufferSize`

The size, in bytes, of buffer.


## Return Value

<b>VmbPacketRestore</b> returns a status code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | NtosKrnl.exe |