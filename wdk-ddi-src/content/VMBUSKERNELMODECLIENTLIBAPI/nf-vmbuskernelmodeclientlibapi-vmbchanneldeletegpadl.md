---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelDeleteGpadl
title: VmbChannelDeleteGpadl
author: windows-driver-content
description: The VmbChannelDeleteGpadl function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the VmbChannelCreateGpadlFromMdl or VmbChannelCreateGpadlFromBuffer functions.
old-location: netvista\vmbchanneldeletegpadl.htm
ms.assetid: B1446A29-F2C1-4F08-8B38-5BE9188F5132
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbChannelDeleteGpadl
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
ms.keywords: VmbChannelDeleteGpadl
req.iface: 
req.product: Windows 10 or later.
---

# VmbChannelDeleteGpadl function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>VmbChannelDeleteGpadl</b> function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the <a href="https://msdn.microsoft.com/6C63E250-1A11-45E8-B535-263806DA4A33">VmbChannelCreateGpadlFromMdl</a> or
<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a> functions. If the GPADL is currently mapped to the server, this function is blocked until the GPADL is unmapped.</p>


## -syntax

````
VOID VmbChannelDeleteGpadl(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     GpadlHandle
);
````


## -parameters
<dl>

### -param <i>Channel</i> [in]

<dd>
<p>A handle for a channel.</p>
</dd>

### -param <i>GpadlHandle</i> [in]

<dd>
<p>The GPADL handle of the GPADL to delete.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.13</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
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
<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6C63E250-1A11-45E8-B535-263806DA4A33">VmbChannelCreateGpadlFromMdl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelDeleteGpadl function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
