---
UID: NF:ndis.NdisClDeregisterSap
title: NdisClDeregisterSap function
author: windows-driver-content
description: NdisClDeregisterSap releases a previously registered SAP.
old-location: netvista\ndisclderegistersap.htm
old-project: netvista
ms.assetid: ee3eb668-04f5-4731-b0bd-5cc8a9d4407f
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisClDeregisterSap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClDeregisterSap (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClDeregisterSap (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisClDeregisterSap
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Protocol_Driver_Function
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

# NdisClDeregisterSap function



## -description
<b>NdisClDeregisterSap</b> releases a previously registered SAP.



## -syntax

````
NDIS_STATUS NdisClDeregisterSap(
  _In_ NDIS_HANDLE NdisSapHandle
);
````


## -parameters

### -param NdisSapHandle [in]

Specifies the handle returned by 
     <b>NdisClRegisterSap</b>.


## -returns
<b>NdisClDeregisterSap</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>The call manager's 
       <a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">
       ProtocolCmDeregisterSap</a> function has been called to complete the requested operation. NDIS calls
       the client's 
       <a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
       ProtocolClDeregisterSapComplete</a> function when this operation is completed.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The SAP already is being closed, so this is a redundant call. If 
       <b>NdisClRegisterSap</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
       internal call to its 
       <i>ProtocolClRegisterSapComplete</i> function.

 


## -remarks
<b>NdisClDeregisterSap</b> releases a SAP on which the client previously registered itself to receive
    incoming calls with 
    <b>NdisClRegisterSap</b>.

The client should consider the given 
    <i>NdisSapHandle</i> invalid as soon as it calls 
    <b>NdisClDeregisterSap</b>.


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
   <a href="https://msdn.microsoft.com/4803a368-5a00-4bfe-b97f-9534e8282f73">NdisClDeregisterSap (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisClDeregisterSap (NDIS
   5.1)</b>) in Windows XP.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547996">Irql_Protocol_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmregistersapcomplete.md">NdisCmRegisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
   ProtocolClDeregisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">ProtocolCmDeregisterSap</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClDeregisterSap function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

