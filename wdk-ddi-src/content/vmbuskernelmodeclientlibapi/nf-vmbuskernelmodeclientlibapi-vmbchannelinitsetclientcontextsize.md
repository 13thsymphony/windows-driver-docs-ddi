---
UID : NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetClientContextSize
title : VmbChannelInitSetClientContextSize function
author : windows-driver-content
description : The VmbChannelInitSetClientContextSize function sets the size of the optional context area allocated for the client driver on each incoming packet.
old-location : netvista\vmbchannelinitsetclientcontextsize.htm
old-project : netvista
ms.assetid : 6AABB3EB-F61A-40DA-BA9F-2AB91FC4B89E
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : VmbChannelInitSetClientContextSize function [Network Drivers Starting with Windows Vista], VmbChannelInitSetClientContextSize, vmbuskernelmodeclientlibapi/VmbChannelInitSetClientContextSize, netvista.vmbchannelinitsetclientcontextsize
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
req.lib : Vmbkmcl.lib
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


# VmbChannelInitSetClientContextSize function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetClientContextSize</b> function sets the size of the optional context area allocated for the client driver
on each incoming packet.

## Syntax

````
NTSTATUS
 VmbChannelInitSetClientContextSize(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     ContextSize
);
````

## Parameters

`Channel`

A handle for a channel.

`ContextSize`

The size of the context area allocated on each packet     object.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |