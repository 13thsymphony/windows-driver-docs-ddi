---
UID: NF.wsk.WskReleaseProviderNPI
title: WskReleaseProviderNPI
author: windows-driver-content
description: The WskReleaseProviderNPI function releases a Network Programming Interface (NPI) that was captured with WskCaptureProviderNPI.
old-location: netvista\wskreleaseprovidernpi.htm
old-project: netvista
ms.assetid: 6b0b995a-61db-4bdf-a896-74d91bd192e7
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WskReleaseProviderNPI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskReleaseProviderNPI
req.alt-loc: Netio.lib,Netio.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WskReleaseProviderNPI function



## -description
<p>The 
  <b>WskReleaseProviderNPI</b> function releases a 
  <a href="netvista.network_programming_interface">Network Programming Interface
  (NPI)</a> that was captured with 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff571122">WskCaptureProviderNPI</a>.</p>


## -syntax

````
VOID WskReleaseProviderNPI(
  _In_ PWSK_REGISTRATION WskRegistration
);
````


## -parameters
<dl>

### -param <i>WskRegistration</i> [in]

<dd>
<p>A pointer to the memory location initialized by 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571143">WskRegister</a> that identifies a WSK
     application's registration instance.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>For each call to
    <b>WskCaptureProviderNPI</b> that returns a success code, there must be exactly one corresponding 
    <b>WskReleaseProviderNPI</b> call that uses
    the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskCaptureProviderNPI</b>.</p>

<p>For each call to
    <b>WskCaptureProviderNPI</b> that returns a success code, there must be exactly one corresponding 
    <b>WskReleaseProviderNPI</b> call that uses
    the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskCaptureProviderNPI</b>.</p>

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
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Netio.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571122">WskCaptureProviderNPI</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571178">WSK_REGISTRATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WskReleaseProviderNPI function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
