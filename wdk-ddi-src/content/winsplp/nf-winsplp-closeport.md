---
UID: NF.winsplp.ClosePort
title: ClosePort
author: windows-driver-content
description: A language or port monitor's ClosePort function closes a printer port.
old-location: print\closeport.htm
old-project: print
ms.assetid: 1d63f36d-4c62-40e9-b3c0-f6d847340b07
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: ClosePort
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
req.alt-api: ClosePort
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

# ClosePort function



## -description
<p>A language or port monitor's <b>ClosePort</b> function closes a printer port.</p>


## -syntax

````
BOOL ClosePort(
  _In_ HANDLE hPort
);
````


## -parameters
<dl>

### -param <i>hPort</i> [in]

<dd>
<p>Caller-supplied pointer to a port handle.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.</p>

## -remarks
<p>
<a href="NULL">Language monitors</a> and port monitor server DLLs are required to define a <b>ClosePort</b> function and include the function's address in a <a href="..\winsplp\ns-winsplp--monitor2.md">MONITOR2</a> structure.</p>

<p>The handle received as the function's <i>hPort</i> argument is the port handle that the monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> or <a href="print.openportex">OpenPortEx</a> function supplied.</p>

<p>The <b>ClosePort</b> function should close the port by making the received port handle invalid. It should also free all system resources that were allocated by the monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> or <a href="print.openportex">OpenPortEx</a> function.</p>

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
<a href="..\winsplp\ns-winsplp--monitor2.md">MONITOR2</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a>
</dt>
<dt>
<a href="print.openportex">OpenPortEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20ClosePort function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
