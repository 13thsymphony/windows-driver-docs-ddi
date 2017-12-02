---
UID: NF.upssvc.UPSStop
title: UPSStop
author: windows-driver-content
description: The UPSStop function causes a UPS minidriver to stop monitoring its UPS unit.
old-location: battery\upsstop.htm
old-project: battery
ms.assetid: 55555e58-eaba-4c39-a771-9924da3fcfc4
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: UPSStop
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UPSStop
req.alt-loc: Upssvc.h
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

# UPSStop function



## -description
<p>The <b>UPSStop</b> function causes a UPS minidriver to stop monitoring its UPS unit.</p>


## -syntax

````
void UPSStop(
   void 
);
````


## -parameters
<dl>

### -param  

<dd>
<p>None</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>UPSStop</b> function must:</p>

<p>Cancel all waiting calls to <a href="..\upssvc\nf-upssvc-upswaitforstatechange.md">UPSWaitForStateChange</a>.</p>

<p>Stop monitoring the UPS unit.</p>

<p>Close and release the UPS unit's COM port.</p>

<p>After <b>UPSStop</b> returns, the only function the UPS service can call is <a href="..\upssvc\nf-upssvc-upsinit.md">UPSInit</a>. </p>

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
<dt>Upssvc.h (include Upssvc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\upssvc\nf-upssvc-upsinit.md">UPSInit</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20UPSStop function%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
