---
UID: NF.winsplp.InitializePrintMonitorUI
title: InitializePrintMonitorUI
author: windows-driver-content
description: A port monitor UI DLL's InitializePrintMonitorUI function supplies the print spooler with addresses of DLL functions.
old-location: print\initializeprintmonitorui.htm
old-project: print
ms.assetid: baa80f8c-68ed-43a3-8c82-79a4388f9ab6
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: InitializePrintMonitorUI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: InitializePrintMonitorUI
req.alt-loc: Winsplp.h
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

# InitializePrintMonitorUI function



## -description
<p>A port monitor UI DLL's <b>InitializePrintMonitorUI</b> function supplies the print spooler with addresses of DLL functions.</p>


## -syntax

````
PMONITORUI WINAPI InitializePrintMonitorUI(
    void
);
````


## -parameters
<dl>

### -param void 

<dd></dd>
</dl>

## -returns
<p>The function should return a pointer to an initialized <a href="..\winsplp\ns-winsplp--monitorui.md">MONITORUI</a> structure.</p>

## -remarks
<p>Port monitor UI DLLs are required to export an <b>InitializePrintMonitorUI</b> function. The function is called immediately after the DLL is loaded, and is not called again until the DLL is reloaded. Its purposes are to allow the DLL to initialize itself, and to provide the spooler with pointers to internal functions.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<a href="..\winsplp\nf-winsplp-initializeprintmonitor.md">InitializePrintMonitor</a>
</dt>
<dt>
<a href="..\winsplp\ns-winsplp--monitorui.md">MONITORUI</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20InitializePrintMonitorUI function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
