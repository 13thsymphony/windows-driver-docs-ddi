---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelSetPointer
title: VmbChannelSetPointer
author: windows-driver-content
description: The VmbChannelSetPointer function saves an arbitrary pointer in a channel context.
old-location: netvista\vmbchannelsetpointer.htm
old-project: netvista
ms.assetid: E536B66D-EAF2-4377-8452-7D37A277E7C8
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: VmbChannelSetPointer
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
req.alt-api: VmbChannelSetPointer
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
req.iface: 
req.product: Windows 10 or later.
---

# VmbChannelSetPointer function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>VmbChannelSetPointer</b> function saves an arbitrary pointer in a channel
context.  </p>


## -syntax

````
VOID VmbChannelSetPointer(
  _In_     VMBCHANNEL             Channel,
  _In_opt_ __drv_aliasesMem PVOID Pointer
);
````


## -parameters
<dl>

### -param <i>Channel</i> [in]

<dd>
<p>A handle for a channel.  </p>
</dd>

### -param <i>Pointer</i> [in, optional]

<dd>
<p>Arbitrary pointer to save in the channel's context.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks
<p>  This is intended to be a more efficient way for a client driver to retrieve client driver's context.  For more information, see the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelgetpointer.md">VmbChannelGetPointer</a> function.</p>

<p>  This is intended to be a more efficient way for a client driver to retrieve client driver's context.  For more information, see the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelgetpointer.md">VmbChannelGetPointer</a> function.</p>

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
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelgetpointer.md">VmbChannelGetPointer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelSetPointer function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
