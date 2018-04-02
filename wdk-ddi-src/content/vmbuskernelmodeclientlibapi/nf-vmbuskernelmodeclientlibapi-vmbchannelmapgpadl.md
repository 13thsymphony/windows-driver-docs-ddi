---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelMapGpadl
title: VmbChannelMapGpadl function
author: windows-driver-content
description: The VmbChannelMapGpadl function maps a client-side buffer into server-side physical address space by using a Guest Physical Address Descriptor List (GPADL) number.
old-location: netvista\vmbchannelmapgpadl.htm
old-project: netvista
ms.assetid: A7801EE9-BFDB-4F77-9DA4-A6612F63AD48
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY, VmbChannelMapGpadl, VmbChannelMapGpadl function [Network Drivers Starting with Windows Vista], netvista.vmbchannelmapgpadl, vmbuskernelmodeclientlibapi/VmbChannelMapGpadl
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
-	VmbChannelMapGpadl
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbChannelMapGpadl function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelMapGpadl</b>  function maps a client-side buffer into server-side physical address space by using a Guest Physical Address Descriptor List (GPADL) number.

## Syntax

```
NTSTATUS VmbChannelMapGpadl(
  VMBCHANNEL Channel,
  UINT32     Flags,
  UINT32     GpadlHandle,
  PMDL       *Mdl
);
```

## Parameters

`Channel`

A handle for a channel.

`Flags`

Flags.  The possible flag values are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY"></a><a id="vmbus_channel_gpadl_flag_read_only"></a><dl>
<dt><b>VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
Map with read-only access. 

</td>
</tr>
</table>
 

If
this flag value is not set, the function tries to map the GPADL for write access. If the GPADL was not
created with write access, this mapping attempt fails. The
caller is not prevented from writing to the buffer if this flag is set. This scheme is used to improve the performance of live migration
and snapshotting.

`GpadlHandle`

The GPADL handle of the GPADL to map.

`Mdl`

A pointer to a MDL describing the client buffer. This
buffer is only mapped into physical address space. The caller must take
additional steps to map it into virtual address space.


## Return Value

None

## Remarks

The GPADL must have been pre-established by the client, for instance, by using the <a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a> function.  

Only a single mapping may exist for any given GPADL at a time.  

You must pair calls to this
function with calls to the <a href="https://msdn.microsoft.com/EE300158-D7D8-4353-B205-362232A22568">VmbChannelUnmapGpadl</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |

## See Also

<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a>



<a href="https://msdn.microsoft.com/EE300158-D7D8-4353-B205-362232A22568">VmbChannelUnmapGpadl</a>