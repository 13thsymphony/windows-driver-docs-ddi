---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSaveContinue
title: VmbChannelSaveContinue function
author: windows-driver-content
description: The VmbChannelSaveContinue function saves the channel state to a buffer. Run the VmbChannelSaveBegin before you run this function. The driver must check the return value of the function.
old-location: netvista\vmbchannelsavecontinue.htm
old-project: netvista
ms.assetid: 57266CAE-C069-4379-92FD-0F93FECC6EB5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbChannelSaveContinue, VmbChannelSaveContinue function [Network Drivers Starting with Windows Vista], netvista.vmbchannelsavecontinue, vmbuskernelmodeclientlibapi/VmbChannelSaveContinue
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	VmbChannelSaveContinue
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbChannelSaveContinue function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveContinue</b> function saves the channel state to a buffer.  Run the <a href="https://msdn.microsoft.com/A0946287-3ED2-4DE1-A3D7-46611B25BB93">VmbChannelSaveBegin</a> before you run this function. The driver must check the return value of the function.

## Syntax

```
NTSTATUS VmbChannelSaveContinue(
  VMBCHANNEL Channel,
  PVOID      SaveBuffer,
  ULONG      SaveBufferSize,
  PULONG     BytesFilled,
  PULONG     BytesRequired
);
```

## Parameters

`Channel`

A handle for a channel to save.

`SaveBuffer`

A pointer to buffer into which to save state information.

`SaveBufferSize`

The size, in bytes, of the save buffer.

`BytesFilled`

A pointer to a variable that receives the number of bytes
that were copied to the save buffer.

`BytesRequired`

A pointer to a variable that receives the number of
bytes that are needed for this function to make progress on the next
call.


## Return Value

<b>VmbChannelSaveContinue</b> returns the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The state was saved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL </b></dt>
</dl>
</td>
<td width="60%">
The save buffer was too small.  The <i>BytesNeeded</i>
parameter     contains the number of bytes that are required to make any progress.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
Some data was written to the save
buffer, but there is more data to be saved.

</td>
</tr>
</table>

## Remarks

The save process saves
the data in "chunks" and can continue from the point it stopped. 

If the caller did not allocate enough space in advance, multiple calls may be needed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |

## See Also

<a href="https://msdn.microsoft.com/A0946287-3ED2-4DE1-A3D7-46611B25BB93">VmbChannelSaveBegin</a>