---
UID : NF:vmbuskernelmodeclientlibapi.VmbChannelCreateGpadlFromBuffer
title : VmbChannelCreateGpadlFromBuffer function
author : windows-driver-content
description : The VmbChannelCreateGpadlFromBuffer function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used in the server to access the buffer.
old-location : netvista\vmbchannelcreategpadlfrombuffer.htm
old-project : netvista
ms.assetid : B45E2463-1EBC-4F32-B3AD-8331E664BB24
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : VmbChannelCreateGpadlFromBuffer
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
req.alt-api : VmbChannelCreateGpadlFromBuffer
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


# VmbChannelCreateGpadlFromBuffer function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCreateGpadlFromBuffer</b> function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used
in the server to access the buffer.

## Syntax

````
NTSTATUS
 VmbChannelCreateGpadlFromBuffer(
  _In_  VMBCHANNEL                    Channel,
  _In_  UINT32                        Flags,
  _In_  reads_bytes_(ByteCount) PVOID Buffer,
  _In_  UINT32                        ByteCount,
  _Out_ PUINT32                       GpadlHandle
);
````

## Parameters

`Channel`

A handle for a channel.

`Flags`

Flags. The possible values are the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

`Buffer`

The buffer, which is probed and locked
until the GPADL is torn down.

`ByteCount`

The length of the buffer, in bytes.

`GpadlHandle`

A GPADL handle of the created Memory Descriptor List (MDL). Send this to the server to use with the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl.md">VmbChannelMapGpadl</a> function.


## Return Value

None

## Remarks

When this function returns, the server
endpoint can call <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl.md">VmbChannelMapGpadl</a>, because VMBus will already have sent
the GPADL description to the opposite endpoint and received confirmation.


The GPADL must be deleted by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchanneldeletegpadl.md">VmbChannelDeleteGpadl</a> function.

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
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchanneldeletegpadl.md">VmbChannelDeleteGpadl</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl.md">VmbChannelMapGpadl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelCreateGpadlFromBuffer function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>