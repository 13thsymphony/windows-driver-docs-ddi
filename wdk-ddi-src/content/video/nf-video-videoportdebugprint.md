---
UID: NF:video.VideoPortDebugPrint
title: VideoPortDebugPrint function
author: windows-driver-content
description: Video miniport drivers should not call the VideoPortDebugPrint function. Instead, they should call the VideoDebugPrint macro.
old-location: display\videoportdebugprint.htm
old-project: display
ms.assetid: c476c8a2-5d79-45cd-ae72-f8792137f9c2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortDebugPrint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortDebugPrint
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

# VideoPortDebugPrint function



## -description
Video miniport drivers should not call the <b>VideoPortDebugPrint</b> function. Instead, they should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570170">VideoDebugPrint</a> macro.



## -syntax

````
VOID VideoPortDebugPrint(
       VIDEO_DEBUG_LEVEL DebugPrintLevel,
  _In_ PSTR              DebugMessage
);
````


## -parameters

### -param DebugPrintLevel 


### -param DebugMessage [in]

Pointer to a string that contains the debug message.


## -returns
None


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
Available in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h</dt>
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