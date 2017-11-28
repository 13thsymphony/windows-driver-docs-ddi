---
UID: NF.bdasup.BdaUninitFilter
title: BdaUninitFilter
author: windows-driver-content
description: The BdaUninitFilter function removes the BDA filter context from the associated filter instance.
old-location: stream\bdauninitfilter.htm
old-project: stream
ms.assetid: c74f5633-49bf-4c8d-8702-89723067753a
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: BdaUninitFilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BdaUninitFilter
req.alt-loc: Bdasup.lib,Bdasup.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# BdaUninitFilter function



## -description
<p>The <b>BdaUninitFilter</b> function removes the BDA filter context from the associated filter instance. </p>


## -syntax

````
NTSTATUS BdaUninitFilter(
  _In_ PKSFILTER pKSFilter
);
````


## -parameters
<dl>

### -param <i>pKSFilter</i> [in]

<dd>
<p>Points to the filter from which to remove the BDA filter context.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS or an appropriate error code. </p>

## -remarks
<p>The <b>BdaUninitFilter</b> function exists only to support legacy drivers and is, therefore, obsolete. That is, new BDA minidriver implementations should not call <b>BdaUninitFilter</b>. </p>

<p>In Windows XP and later, the BDA support driver (<i>Bdasup.sys</i>) automatically handles removing the BDA filter context associated with a filter instance. When a BDA minidriver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556464">BdaInitFilter</a>, the BDA support driver creates its own BDA filter context. This BDA filter context is hidden from the BDA minidriver. However, when required, the BDA support driver can access this BDA filter context. The BDA support driver adds a pointer to this BDA filter context to the object bag for the associated <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> object. When the associated KSFILTER object is destroyed, AVStream requests that the BDA support driver delete this BDA filter context from the object bag. In this way, the BDA support driver can destroy this BDA filter context without requiring intervention by the BDA minidriver.</p>

<p>The <b>BdaUninitFilter</b> function exists only to support legacy drivers and is, therefore, obsolete. That is, new BDA minidriver implementations should not call <b>BdaUninitFilter</b>. </p>

<p>In Windows XP and later, the BDA support driver (<i>Bdasup.sys</i>) automatically handles removing the BDA filter context associated with a filter instance. When a BDA minidriver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556464">BdaInitFilter</a>, the BDA support driver creates its own BDA filter context. This BDA filter context is hidden from the BDA minidriver. However, when required, the BDA support driver can access this BDA filter context. The BDA support driver adds a pointer to this BDA filter context to the object bag for the associated <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> object. When the associated KSFILTER object is destroyed, AVStream requests that the BDA support driver delete this BDA filter context from the object bag. In this way, the BDA support driver can destroy this BDA filter context without requiring intervention by the BDA minidriver.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bdasup.h (include Bdasup.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Bdasup.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556464">BdaInitFilter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaUninitFilter function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
