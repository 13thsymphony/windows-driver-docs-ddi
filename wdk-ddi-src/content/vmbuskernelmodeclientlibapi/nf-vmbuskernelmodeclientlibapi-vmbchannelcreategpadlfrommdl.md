---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelCreateGpadlFromMdl
title: VmbChannelCreateGpadlFromMdl function
author: windows-driver-content
description: The VmbChannelCreateGpadlFromMdl function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used in the server to access the buffer.
old-location: netvista\vmbchannelcreategpadlfrommdl.htm
old-project: NetVista
ms.assetid: 6C63E250-1A11-45E8-B535-263806DA4A33
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: VmbChannelCreateGpadlFromMdl
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
req.alt-api: VmbChannelCreateGpadlFromMdl
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
req.irql: 
req.product: Windows 10 or later.
---

# VmbChannelCreateGpadlFromMdl function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCreateGpadlFromMdl</b> function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used
in the server to access the buffer.  



## -syntax

````
NTSTATUS VmbChannelCreateGpadlFromMdl(
  _In_  VMBCHANNEL Channel,
  _In_  UINT32     Flags,
  _In_  PMDL       Mdl,
  _In_  UINT32     StartOffsetWithinMdl,
  _In_  UINT32     DataLengthWithinMdl,
  _Out_ PUINT32    GpadlHandle
);
````


## -parameters

### -param Channel [in]

A handle for a channel.  


### -param Flags [in]

Flags. The possible values are the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param VMBUS_CHANNEL_GPADL_READ_ONLY

</td>
<td width="60%">
If you specify this value, the buffer is read-only. Otherwise, the server can write to the buffer. This is not a security measure, but can improve snapshot and live migration performance.

</td>
</tr>
</table>
 


### -param Mdl [in]

 A pointer to a Memory Descriptor List (MDL) chain that describes the buffer. The buffer may
have multiple pieces, which are chained by using the MDL next pointer.



### -param StartOffsetWithinMdl [in]

An offset, in bytes, in the MDL at which to start the mapping.



### -param DataLengthWithinMdl [in]

The length, in bytes, of the buffer chain. If this value is zero (0),
use until the end of the MDL.



### -param GpadlHandle [out]

The GPADL handle of the created MDL. Send this to the server to use with the <a href="netvista.vmbchannelmapgpadl">VmbChannelMapGpadl</a> function.


## -remarks
When this function returns, the server
endpoint can call <a href="netvista.vmbchannelmapgpadl">VmbChannelMapGpadl</a>, because VMBus will already have send
the GPADL description to the opposite endpoint and received confirmation.


 The GPADL must be deleted by using the <a href="netvista.vmbchanneldeletegpadl">VmbChannelDeleteGpadl</a> function.


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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.vmbchanneldeletegpadl">VmbChannelDeleteGpadl</a>
</dt>
<dt>
<a href="netvista.vmbchannelmapgpadl">VmbChannelMapGpadl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20VmbChannelCreateGpadlFromMdl function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

