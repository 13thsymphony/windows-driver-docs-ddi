---
UID: NF.winsplp.XcvOpenPort
title: XcvOpenPort
author: windows-driver-content
description: A port monitor server DLL's XcvOpenPort function opens a port for configuration operations.
old-location: print\xcvopenport.htm
old-project: print
ms.assetid: ba0f5820-08eb-40c7-9593-7434ee0e29c6
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: XcvOpenPort
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
req.alt-api: XcvOpenPort
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

# XcvOpenPort function



## -description
<p>A port monitor server DLL's <b>XcvOpenPort</b> function opens a port for configuration operations.</p>


## -syntax

````
BOOL XcvOpenPort(
   HANDLE      hMonitor,
   LPCWSTR     pszObject,
   ACCESS_MASK GrantedAccess,
   PHANDLE     phXcv
);
````


## -parameters
<dl>

### -param hMonitor 

<dd>
<p>Caller supplied monitor instance handle. This is the handle returned by the monitor's <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> function. (This parameter does not exist if the print monitor supports <b>InitializePrintMonitor</b> instead of <b>InitializePrintMonitor2</b>.)</p>
</dd>

### -param pszObject 

<dd>
<p>Caller-supplied pointer to a string representing the name of the port. Can be <b>NULL</b>, and most monitors do not need this parameter.</p>
</dd>

### -param GrantedAccess 

<dd>
<p>Caller-supplied ACCESS_MASK structure containing the access granted to the user during a print monitor UI DLL's call to the spooler's <b>OpenPrinter</b> function. See the following Remarks section.</p>
</dd>

### -param phXcv 

<dd>
<p>Caller-supplied pointer to a location to receive a function-supplied port handle.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.</p>

## -remarks
<p>Port monitor server DLLs are required to define an <b>XcvOpenPort</b> function and include its address in a <a href="..\winsplp\ns-winsplp--monitor2.md">MONITOR2</a> structure.</p>

<p>The spooler's <b>OpenPrinter</b> function (described in the Microsoft Windows SDK documentation) calls <b>XcvOpenPort</b> if the specified printer name includes either of the strings "XcvPort" or "XcvMonitor". For more information, see <a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>.</p>

<p>The <b>XcvOpenPort</b> function should open the port for configuration purposes. This operation might only consist of storing the input arguments for subsequent use within <a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a>. The function should return a handle to the stored information in the location pointed to by <i>phXcv</i>. This handle is returned to the caller of <b>OpenPrinter</b>, and subsequently received as an input argument to <b>XcvDataPort</b>.</p>

<p>The function should save the granted access mask. Later, when the server DLL's <b>XcvDataPort</b> function is called, the granted access should be compared with SERVER_ACCESS_ADMINISTER and if the comparison fails, <b>XcvDataPort</b> should return ERROR_ACCESS_DENIED.</p>

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
<a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20XcvOpenPort function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
