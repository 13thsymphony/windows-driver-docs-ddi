---
UID: NF.winsplp.OpenPort
title: OpenPort function
author: windows-driver-content
description: A port monitor's OpenPort function opens a printer port.
old-location: print\openport.htm
old-project: print
ms.assetid: 32e47d3a-83ad-4d3f-a6ce-c03712021844
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: OpenPort
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
req.alt-api: pfnOpenPort
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
req.product: Windows 10 or later.
---

# OpenPort function



## -description
A port monitor's <code>OpenPort</code> function opens a printer port.



## -syntax

````
BOOL WINAPI pfnOpenPort(
   HANDLE  hMonitor,
   LPWSTR  pName,
   PHANDLE pHandle
);
````


## -parameters

### -param hMonitor 

Caller supplied monitor instance handle. This is the handle returned by the monitor's <a href="print.initializeprintmonitor2">InitializePrintMonitor2</a> function. (This parameter does not exist if the print monitor supports <b>InitializePrintMonitor</b> instead of <b>InitializePrintMonitor2</b>.)


### -param pName 

Caller-supplied pointer to a string containing the name of the port to be opened.


### -param pHandle 

Caller-supplied pointer to a location to receive a port handle.


## -returns
If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.


## -remarks
Port monitor server DLLs are required to define an <code>OpenPort</code> function and include the function's address in a <a href="print.monitor2">MONITOR2</a> structure.

The <code>OpenPort</code> function is called, either by a language monitor or by the print spooler, when a print queue is being connected to a port. The <code>OpenPort</code> function's primary purpose is to return a port handle that the caller can use as an input argument for subsequent calls to the port monitor's <a href="print.startdocport">StartDocPort</a>, <a href="print.writeport">WritePort</a>, <a href="print.readport">ReadPort</a>, <a href="print.enddocport">EndDocPort</a>, and <a href="print.getprinterdatafromport">GetPrinterDataFromPort</a> functions.

Besides returning a port handle, the <code>OpenPort</code> function can perform initialization operations that need to be taken care of before read or write operations are performed. For example, if the port supports modifiable time-out values, the <code>OpenPort</code> function should set these values.

Calls to <code>OpenPort</code> are not print job-specific. Between each call to a port monitor's <code>OpenPort</code> and <a href="print.closeport">ClosePort</a> functions, there can be multiple calls to its <b>StartDocPort</b> and <b>EndDocPort</b> functions.

You can assume that after the print spooler has called <code>OpenPort</code> with a particular port name, it will not call <code>OpenPort</code> again with the same port name before calling <b>ClosePort</b>.

Print monitor functions that accept a port handle as input do not also accept a monitor handle. Therefore, the <code>OpenPort</code> function must store the received monitor handle in a location that can be referenced by the port handle. This allows the functions that accept a port handle to reference the monitor handle.


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
Header

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
<a href="print.initializeprintmonitor2">InitializePrintMonitor2</a>
</dt>
<dt>
<a href="print.openportex">OpenPortEx</a>
</dt>
<dt>
<a href="print.setporttimeouts">SetPortTimeOuts</a>
</dt>
<dt>
<a href="print.startdocport">StartDocPort</a>
</dt>
<dt>
<a href="print.writeport">WritePort</a>
</dt>
<dt>
<a href="print.readport">ReadPort</a>
</dt>
<dt>
<a href="print.enddocport">EndDocPort</a>
</dt>
<dt>
<a href="print.getprinterdatafromport">GetPrinterDataFromPort</a>
</dt>
<dt>
<a href="print.closeport">ClosePort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20OpenPort function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

