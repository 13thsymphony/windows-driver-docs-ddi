---
UID: NS.winsplp._MONITOREX
title: MONITOREX
author: windows-driver-content
description: The MONITOREX structure is obsolete and supported for compatibility purposes only.
old-location: print\monitorex.htm
old-project: print
ms.assetid: f03f72a8-8dc1-4e27-b89b-1afea16a177a
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: MONITOREX, MONITOREX, *LPMONITOREX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MONITOREX
req.alt-loc: winsplp.h
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

# MONITOREX structure



## -description
<p>The MONITOREX structure is obsolete and supported for compatibility purposes only. New print monitors should implement <a href="https://msdn.microsoft.com/library/windows/hardware/ff551605">InitializePrintMonitor2</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff557532">MONITOR2</a> so that they can be used with print server clusters.</p>
<p>The MONITOREX structure is used as the return value for a print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551600">InitializePrintMonitor</a> function.</p>


## -syntax

````
typedef struct _MONITOREX {
  DWORD   dwMonitorSize;
  MONITOR Monitor;
} MONITOREX, *LPMONITOREX;
````


## -struct-fields
<dl>

### -field <b>dwMonitorSize</b>

<dd>
<p>Specifies the size, in bytes, of the Monitor <b>member</b>.</p>
</dd>

### -field <b>Monitor</b>

<dd>
<p>Is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542552">MONITOR</a> structure.</p>
</dd>
</dl>

## -remarks
<p>Print monitors are responsible for filling in the MONITOREX and MONITOR structures.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Winsplp.h (include Winsplp.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542552">MONITOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITOREX structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
