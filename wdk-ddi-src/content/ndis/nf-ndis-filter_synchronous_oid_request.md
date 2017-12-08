---
UID: NF.ndis.FILTER_SYNCHRONOUS_OID_REQUEST
title: FILTER_SYNCHRONOUS_OID_REQUEST function
author: windows-driver-content
description: This callback function is reserved.
old-location: netvista\filter_synchronous_oid_request.htm
old-project: netvista
ms.assetid: AC84B27B-6FBF-429D-A8FA-F3C8F583F738
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FILTER_SYNCHRONOUS_OID_REQUEST
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
req.alt-api: FilterSynchronousOidRequest
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
---

# FILTER_SYNCHRONOUS_OID_REQUEST function



## -description

## -syntax

````
NDIS_STATUS FilterSynchronousOidRequest(
          NDIS_HANDLE      FilterModuleContext,
  _Inout_ NDIS_OID_REQUEST *OidRequest,
  _Out_   PVOID            *CallContext
);
````


## -parameters

### -param FilterModuleContext 

Reserved.

### -param OidRequest [in, out]

Reserved.

### -param CallContext [out]

Reserved.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Windows 10, version 1709
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_SYNCHRONOUS_OID_REQUEST function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
