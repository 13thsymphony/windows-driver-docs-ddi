---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelAllocate
title: VmbChannelAllocate function
author: windows-driver-content
description: The VmbChannelAllocate function allocates a new VMBus channel that has default parameters and callbacks.
old-location: netvista\vmbchannelallocate.htm
old-project: netvista
ms.assetid: 97169CF5-566E-4EF6-88AD-7B68E9FE46EC
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VmbChannelAllocate, VmbChannelAllocate function [Network Drivers Starting with Windows Vista], netvista.vmbchannelallocate, vmbuskernelmodeclientlibapi/VmbChannelAllocate
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbChannelAllocate
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbChannelAllocate function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

 The <b>VmbChannelAllocate</b> function allocates a new VMBus channel that has default parameters and callbacks.

## Syntax

````
NTSTATUS
 VmbChannelAllocate(
  _In_  PDEVICE_OBJECT                                     ParentDeviceObject,
  _In_  BOOLEAN                                            IsServer,
  _Out_ _At_(*Channel, __drv_allocatesMem(Mem)) VMBCHANNEL *Channel
);
````

## Parameters

`ParentDeviceObject`

A pointer to the parent device.

`IsServer`

Whether the new channel is a server endpoint.

`Channel`

A pointer to an allocated channel.


## Return Value

None

## Remarks

The
channel may be further initialized using the VMBus channel initialization routines before
it is enabled by using the  <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a> function. The channel must be freed by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcleanup.md">VmbChannelCleanup</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcleanup.md">VmbChannelCleanup</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelAllocate function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>