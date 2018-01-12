---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelAllocate
title: VmbChannelAllocate function
author: windows-driver-content
description: The VmbChannelAllocate function allocates a new VMBus channel that has default parameters and callbacks.
old-location: netvista\vmbchannelallocate.htm
old-project: netvista
ms.assetid: 97169CF5-566E-4EF6-88AD-7B68E9FE46EC
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: VmbChannelAllocate
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
req.alt-api: VmbChannelAllocate
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
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
req.typenames: *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelAllocate function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

 The <b>VmbChannelAllocate</b> function allocates a new VMBus channel that has default parameters and callbacks. 



## -syntax

````
NTSTATUS
 VmbChannelAllocate(
  _In_  PDEVICE_OBJECT                                     ParentDeviceObject,
  _In_  BOOLEAN                                            IsServer,
  _Out_ _At_(*Channel, __drv_allocatesMem(Mem)) VMBCHANNEL *Channel
);
````


## -parameters

### -param ParentDeviceObject [in]

A pointer to the parent device.



### -param IsServer [in]

Whether the new channel is a server endpoint.



### -param Channel [out]

A pointer to an allocated channel.


## -remarks
The
channel may be further initialized using the VMBus channel initialization routines before
it is enabled by using the  <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a> function. The channel must be freed by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcleanup.md">VmbChannelCleanup</a> function.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.13

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Vmbkmcl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcleanup.md">VmbChannelCleanup</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelAllocate function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

