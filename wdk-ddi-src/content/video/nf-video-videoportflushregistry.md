---
UID: NF:video.VideoPortFlushRegistry
title: VideoPortFlushRegistry function
author: windows-driver-content
description: The VideoPortFlushRegistry function flushes registry keys and values associated with the video miniport driver.
old-location: display\videoportflushregistry.htm
old-project: display
ms.assetid: 8b940eec-dac6-4a01-afc8-73115bf994c3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortFlushRegistry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortFlushRegistry
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortFlushRegistry function



## -description
The <b>VideoPortFlushRegistry</b> function flushes registry keys and values associated with the video miniport driver.



## -syntax

````
VP_STATUS VideoPortFlushRegistry(
   PVOID HwDeviceExtension
);
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's device extension.


## -returns
<b>VideoPortFlushRegistry</b> returns NO_ERROR.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Server 2003 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
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
<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportsetregistryparameters.md">VideoPortSetRegistryParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortFlushRegistry function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

