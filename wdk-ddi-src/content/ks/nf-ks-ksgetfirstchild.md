---
UID: NF.ks.KsGetFirstChild
title: KsGetFirstChild
author: windows-driver-content
description: The KsGetFirstChild function returns the first AVStream child object of Object.
old-location: stream\ksgetfirstchild.htm
old-project: stream
ms.assetid: f7ff16ac-fe20-4998-a8b3-d1d02c418938
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: KsGetFirstChild
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsGetFirstChild
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# KsGetFirstChild function



## -description
<p>The<b> KsGetFirstChild</b> function returns the first AVStream child object of <i>Object</i>.</p>


## -syntax

````
PVOID KsGetFirstChild(
  _In_ PVOID Object
);
````


## -parameters
<dl>

### -param <i>Object</i> [in]

<dd>
<p>The object for which to find the first AVStream child object.</p>
</dd>
</dl>

## -returns
<p><b>KsGetFirstChild</b> returns the first AVStream child object of <i>Object</i>. If no such child object exists, it returns <b>NULL</b>.</p>

## -remarks
<p>To see the hierarchical organization of AVStream objects, see <a href="NULL">AVStream Object Hierarchy</a>.</p>

<p>Minidrivers rarely call this function directly. Those that do must manually perform typecasts to and from PVOID. There are a number of functions that are inline calls to <b>KsGetFirstChild</b> and perform typecasts for you: <a href="https://msdn.microsoft.com/library/windows/hardware/ff561684">KsDeviceGetFirstChildFilterFactory</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff562533">KsFilterFactoryGetFirstChildFilter</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="NULL">Mutexes in AVStream</a>.</p>

<p>To see the hierarchical organization of AVStream objects, see <a href="NULL">AVStream Object Hierarchy</a>.</p>

<p>Minidrivers rarely call this function directly. Those that do must manually perform typecasts to and from PVOID. There are a number of functions that are inline calls to <b>KsGetFirstChild</b> and perform typecasts for you: <a href="https://msdn.microsoft.com/library/windows/hardware/ff561684">KsDeviceGetFirstChildFilterFactory</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff562533">KsFilterFactoryGetFirstChildFilter</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="NULL">Mutexes in AVStream</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562658">KsGetParent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561684">KsDeviceGetFirstChildFilterFactory</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562533">KsFilterFactoryGetFirstChildFilter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562545">KsFilterGetFirstChildPin</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetFirstChild function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
