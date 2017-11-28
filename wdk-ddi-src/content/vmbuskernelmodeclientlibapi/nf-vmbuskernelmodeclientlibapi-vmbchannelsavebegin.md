---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelSaveBegin
title: VmbChannelSaveBegin
author: windows-driver-content
description: The VmbChannelSaveBegin function initializes the context for saving the state of a channel. The driver must check the return value of the function.
old-location: netvista\vmbchannelsavebegin.htm
old-project: netvista
ms.assetid: A0946287-3ED2-4DE1-A3D7-46611B25BB93
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: VmbChannelSaveBegin
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
req.alt-api: VmbChannelSaveBegin
req.alt-loc: VmbusKernelModeClientLibApi.h
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
req.iface: 
req.product: Windows 10 or later.
---

# VmbChannelSaveBegin function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>VmbChannelSaveBegin</b> function initializes the context for saving the state of a channel. The driver must check the return value of the function.</p>


## -syntax

````
NTSTATUS VmbChannelSaveBegin(
  _In_ VMBCHANNEL Channel
    
);
````


## -parameters
<dl>

### -param <i>Channel
    </i> [in]

<dd>
<p>A handle for the channel to save.  </p>
</dd>
</dl>

## -returns
<p><b>VmbChannelSaveBegin</b> returns a status code.</p>

## -remarks
<p>The
caller next calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md"> VmbChannelSaveContinue</a> function multiple times until
all the state is saved, and then calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md">VmbChannelSaveEnd</a> function.</p>

<p>The
caller next calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md"> VmbChannelSaveContinue</a> function multiple times until
all the state is saved, and then calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md">VmbChannelSaveEnd</a> function.</p>

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
</table>

## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md"> VmbChannelSaveContinue</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md">VmbChannelSaveEnd</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelSaveBegin function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
