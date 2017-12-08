---
UID: NF.ndis.FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
title: FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
author: windows-driver-content
description: This callback function is reserved.
old-location: netvista\filter_synchronous_oid_request_complete.htm
old-project: netvista
ms.assetid: E0749F52-CC7C-484D-8350-1986154957C1
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FilterSynchronousOidRequestComplete
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE function



## -description

## -syntax

````
VOID FilterSynchronousOidRequestComplete(
  _In_    NDIS_HANDLE      FilterModuleContext,
  _Inout_ NDIS_OID_REQUEST *OidRequest,
  _Inout_ NDIS_STATUS      *Status,
  _In_    PVOID            CallContext
);
````


## -parameters
<dl>

### -param FilterModuleContext [in]

<dd>
<p>Reserved.</p>
</dd>

### -param OidRequest [in, out]

<dd>
<p>Reserved.</p>
</dd>

### -param Status [in, out]

<dd>
<p>Reserved.</p>
</dd>

### -param CallContext [in]

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows 10, version 1709</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
