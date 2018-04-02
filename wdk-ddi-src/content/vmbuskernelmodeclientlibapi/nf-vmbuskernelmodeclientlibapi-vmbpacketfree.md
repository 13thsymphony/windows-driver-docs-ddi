---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketFree
title: VmbPacketFree function
author: windows-driver-content
description: The VmbPacketFree function releases a packet allocated by using the VmbPacketAllocate function.
old-location: netvista\vmbpacketfree.htm
old-project: netvista
ms.assetid: 15688701-2385-4F17-A944-D398EEF3C277
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbPacketFree, VmbPacketFree function [Network Drivers Starting with Windows Vista], netvista.vmbpacketfree, vmbuskernelmodeclientlibapi/VmbPacketFree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbPacketFree
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbPacketFree function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketFree</b> function releases a packet allocated by using the <a href="https://msdn.microsoft.com/F121A7BC-5504-4CF5-8C8A-0568D6C4F77F">VmbPacketAllocate</a> function.

## Syntax

```
void VmbPacketFree(
  __drv_freesMem(Mem)VMBPACKET VmbPacket
);
```

## Parameters

`VmbPacket`

A pointer to an allocated VMBus packet object.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |

## See Also

<a href="https://msdn.microsoft.com/F121A7BC-5504-4CF5-8C8A-0568D6C4F77F">VmbPacketAllocate</a>