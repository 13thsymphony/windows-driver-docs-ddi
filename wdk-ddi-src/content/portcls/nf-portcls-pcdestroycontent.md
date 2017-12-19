---
UID: NF.portcls.PcDestroyContent
title: PcDestroyContent function
author: windows-driver-content
description: The PcDestroyContent function deletes a DRM content ID that was created by PcCreateContentMixed. Note that this function call is identical in operation to the DrmDestroyContent function, and its parameter definitions and return value are also identical.
old-location: audio\pcdestroycontent.htm
old-project: audio
ms.assetid: 742ee83c-3db4-4d77-a79d-28bcc405746d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcDestroyContent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcDestroyContent function in Microsoft Windows XP and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcDestroyContent
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: 
---

# PcDestroyContent function



## -description
The <b>PcDestroyContent</b> function deletes a DRM content ID that was created by <a href="audio.pccreatecontentmixed">PcCreateContentMixed</a>. Note that this function call is identical in operation to the <a href="audio.drmdestroycontent">DrmDestroyContent</a> function, and its parameter definitions and return value are also identical.



## -syntax

````
PORTCLASSAPI NTSTATUS NTAPI  PcDestroyContent(void);
````


## -parameters


## -returns
See return value definition in <a href="audio.drmdestroycontent">DrmDestroyContent</a>.

See return value definition in <a href="audio.drmdestroycontent">DrmDestroyContent</a>.

See return value definition in <a href="audio.drmdestroycontent">DrmDestroyContent</a>.


## -remarks
For more information, see the comments in <a href="audio.drmdestroycontent">DrmDestroyContent</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
The PortCls system driver implements the PcDestroyContent function in Microsoft Windows XP and later operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Portcls.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.pccreatecontentmixed">PcCreateContentMixed</a>
</dt>
<dt>
<a href="audio.drmdestroycontent">DrmDestroyContent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcDestroyContent function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

