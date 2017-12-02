---
UID: NF.winsplp.XcvClosePort
title: XcvClosePort
author: windows-driver-content
description: A port monitor server DLL's XcvClosePort function closes a printer port that was opened by XcvOpenPort.
old-location: print\xcvcloseport.htm
old-project: print
ms.assetid: 8dfeb2d5-e75e-4e5b-b209-cb23133136f7
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: XcvClosePort
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
req.alt-api: XcvClosePort
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

# XcvClosePort function



## -description
<p>A port monitor server DLL's <code>XcvClosePort</code> function closes a printer port that was opened by <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>.</p>


## -syntax

````
BOOL XcvClosePort(
  _In_ HANDLE hXcv
);
````


## -parameters
<dl>

### -param hXcv [in]

<dd>
<p>Caller-supplied printer handle obtained by calling <b>OpenPrinter</b> (described in the Microsoft Windows SDK documentation). This handle is created and returned by <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.</p>

## -remarks
<p>Port monitor server DLLs are required to define an <code>XcvClosePort</code> function and include its address in a <a href="..\winsplp\ns-winsplp--monitor2.md">MONITOR2</a> structure.</p>

<p>The spooler's <b>ClosePrinter</b> function calls <code>XcvClosePort</code> if the printer name that was specified with a previous call to the <b>OpenPrinter</b> function included either of the strings "XcvPort" or "XcvMonitor". For more information, see <a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>. For more information about the <b>OpenPrinter</b> and <b>ClosePrinter</b> functions, see the Windows SDK documentation.</p>

<p>The function should close the port specified by the handle, and it should make the handle invalid.</p>

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
<a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20XcvClosePort function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
