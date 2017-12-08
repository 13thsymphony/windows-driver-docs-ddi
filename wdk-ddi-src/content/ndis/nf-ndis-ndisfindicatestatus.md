---
UID: NF.ndis.NdisFIndicateStatus
title: NdisFIndicateStatus function
author: windows-driver-content
description: The NdisFIndicateStatus function passes on a filtered status indication from an underlying driver or originates a status indication.
old-location: netvista\ndisfindicatestatus.htm
old-project: netvista
ms.assetid: fd81d777-8479-41e3-8f71-e5f4134b60a0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisFIndicateStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFIndicateStatus
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_StatusIndication_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisFIndicateStatus function



## -description
The 
  <b>NdisFIndicateStatus</b> function passes on a filtered status indication from an underlying driver or
  originates a status indication.


## -syntax

````
VOID NdisFIndicateStatus(
  _In_ NDIS_HANDLE             NdisFilterHandle,
  _In_ PNDIS_STATUS_INDICATION StatusIndication
);
````


## -parameters

### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

### -param StatusIndication [in]

A pointer to an 
     <a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.

## -returns
None

## -remarks
Filter drivers can call 
    <b>NdisFIndicateStatus</b> from the 
    <a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a> function, to pass on a
    filtered status indication to overlying drivers.

To originate status indications, filter drivers call 
    <b>NdisFIndicateStatus</b> without a prior NDIS call to 
    <i>FilterStatus</i>.

A filter driver can call 
    <b>NdisFIndicateStatus</b> after setting its registration attributes and the 
    <a href="netvista.ndisfsetattributes">NdisFSetAttributes</a> function returns.
    The driver must not call 
    <b>NdisFIndicateStatus</b> after it returns from the 
    <a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a> function.

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
Version
</th>
<td width="70%">
Supported in NDIS 6.0 and later.
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
Library
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_irql_statusindication_function">Irql_StatusIndication_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a>
</dt>
<dt>
<a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="netvista.ndisfsetattributes">NdisFSetAttributes</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFIndicateStatus function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
