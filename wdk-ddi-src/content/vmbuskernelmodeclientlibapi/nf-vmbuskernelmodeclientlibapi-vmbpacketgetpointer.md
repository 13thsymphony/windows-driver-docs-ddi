---
UID : NF:vmbuskernelmodeclientlibapi.VmbPacketGetPointer
title : VmbPacketGetPointer function
author : windows-driver-content
description : The VmbPacketGetPointer function retrieves a pointer that was previously saved by using the VmbPacketSetPointer function.
old-location : netvista\vmbpacketgetpointer.htm
old-project : netvista
ms.assetid : 56B9C623-2038-4DD3-AA1B-D9A6E47E06C1
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : VmbPacketGetPointer
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
req.alt-api : VmbPacketGetPointer
req.alt-loc : vmbkmcl.lib,vmbkmcl.dll
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
req.typenames : "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product : Windows 10 or later.
---


# VmbPacketGetPointer function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketGetPointer</b> function retrieves a pointer that was previously
saved by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer.md">VmbPacketSetPointer</a> function.

## Syntax

````
PVOID VmbPacketGetPointer(
  _In_ VMBPACKET PacketObject
);
````

## Parameters

`PacketObject`

The handle of a packet object.


## Return Value

<b>VmbPacketGetPointer</b> returns the value previously saved by using <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer.md">VmbPacketSetPointer</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer.md">VmbPacketSetPointer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbPacketGetPointer function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>