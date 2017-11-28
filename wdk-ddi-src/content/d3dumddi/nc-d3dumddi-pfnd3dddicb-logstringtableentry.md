---
UID: NC.d3dumddi.PFND3DDDICB_LOGSTRINGTABLEENTRY
title: PFND3DDDICB_LOGSTRINGTABLEENTRY
author: windows-driver-content
description: Locates a string table entry that is used by the LogMarkerStringTable function to log an Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.
old-location: display\logmarkerstringtableentry.htm
old-project: display
ms.assetid: 54D1F822-2D82-498D-A50F-A917FA127496
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LogMarkerStringTableEntry
req.alt-loc: D3dumddi.h
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
---

# PFND3DDDICB_LOGSTRINGTABLEENTRY callback



## -description
<p>Locates a string table entry that is used by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-logstringtable.md">LogMarkerStringTable</a> function to log an Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.</p>


## -prototype

````
PFND3DDDICB_LOGSTRINGTABLEENTRY LogMarkerStringTableEntry;

_Check_return_ HRESULT APIENTRY* LogMarkerStringTableEntry(
   HANDLE  hLog,
   UINT    StringIndex,
   LPCWSTR Info
)
{ ... }
````


## -parameters
<dl>

### -param <i>hLog</i> 

<dd>
<p>A handle to the ETW log that is to be written to. Must be the same <i>hLog</i> handle passed to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-logstringtable.md">LogMarkerStringTable</a> function.</p>
</dd>

### -param <i>StringIndex</i> 

<dd>
<p>The offset, in bytes, of the string table entry pointed to by <b>Info</b>. Can be negative if the string is passed along with the marker event.</p>
</dd>

### -param <i>Info</i> 

<dd>
<p>A custom text string embedded in the ETW packet. Can be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>
      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
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
<p>Version</p>
</th>
<td width="70%">
<p>WDDM 1.3 and later</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-logstringtable.md">LogMarkerStringTable</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDICB_LOGSTRINGTABLEENTRY callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
