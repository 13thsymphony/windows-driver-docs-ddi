---
UID: NF:ndis.NdisCmCloseAddressFamilyComplete
title: NdisCmCloseAddressFamilyComplete function
author: windows-driver-content
description: NdisCmCloseAddressFamilyComplete returns the final status of a client's request, for which the CM's ProtocolCmCloseAf function returned NDIS_STATUS_PENDING, to close the AF.
old-location: netvista\ndiscmcloseaddressfamilycomplete.htm
old-project: netvista
ms.assetid: 1aeb2ca5-8c56-4a78-8cd5-a178efa9b014
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisCmCloseAddressFamilyComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmCloseAddressFamilyComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_CallManager_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmCloseAddressFamilyComplete function



## -description
<b>NdisCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the CM's 
  <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function returned
  NDIS_STATUS_PENDING, to close the AF.



## -syntax

````
VOID NdisCmCloseAddressFamilyComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisAfHandle
);
````


## -parameters

### -param Status [in]

The call manager sets this to NDIS_STATUS_SUCCESS.


### -param NdisAfHandle [in]

Specifies the NDIS-supplied handle passed to the call manager's 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function when this
     client originally opened the address family.


## -returns
None


## -remarks
A stand-alone call manager must call 
    <b>NdisCmCloseAddressFamilyComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the CM's call to 
    <b>NdisCmCloseAddressFamilyComplete</b> causes a call to that client's 
    <a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">
    ProtocolClCloseAfComplete</a> function.

After a call to 
    <b>NdisCmCloseAddressFamilyComplete</b>, the call manager cannot subsequently use the 
    <i>NdisAfHandle</i>, which becomes invalid for the call manager as soon as this call occurs.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmCloseAddressFamilyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> instead.


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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/1231b255-9d4c-44da-8341-f5024e2eadd5">
   NdisCmCloseAddressFamilyComplete (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>
   NdisCmCloseAddressFamilyComplete (NDIS 5.1)</b>) in Windows XP.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547917">Irql_CallManager_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmcloseaddressfamilycomplete.md">
   NdisMCmCloseAddressFamilyComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">ProtocolClCloseAfComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmCloseAddressFamilyComplete function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

