---
UID: NF:portcls.PcGetContentRights
title: PcGetContentRights function
author: windows-driver-content
description: The PcGetContentRights function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the DrmGetContentRights function, and its parameter definitions and return value are also identical.
old-location: audio\pcgetcontentrights.htm
old-project: audio
ms.assetid: a4e8aee0-d3ac-4086-99a3-a0339b198372
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcGetContentRights
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcGetContentRights function in Microsoft Windows XP and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcGetContentRights
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
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# PcGetContentRights function



## -description
The <b>PcGetContentRights</b> function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a> function, and its parameter definitions and return value are also identical.



## -syntax

````
PORTCLASSAPI NTSTATUS NTAPI  PcGetContentRights(void);
````


## -parameters


## -returns
See return value definition in <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>.

See return value definition in <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>.

See return value definition in <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>.


## -remarks
For more information, see the comments in <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>.


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
The PortCls system driver implements the PcGetContentRights function in Microsoft Windows XP and later operating systems.

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
<a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcGetContentRights function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

