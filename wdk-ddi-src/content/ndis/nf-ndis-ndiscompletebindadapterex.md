---
UID: NF:ndis.NdisCompleteBindAdapterEx
title: NdisCompleteBindAdapterEx function
author: windows-driver-content
description: A protocol driver calls the NdisCompleteBindAdapterEx function to complete a binding operation for which the driver's ProtocolBindAdapterEx function returned NDIS_STATUS_PENDING.
old-location: netvista\ndiscompletebindadapterex.htm
old-project: netvista
ms.assetid: e52c7aeb-bbd8-402e-94af-f74df6deb23c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisCompleteBindAdapterEx
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
req.alt-api: NdisCompleteBindAdapterEx
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

# NdisCompleteBindAdapterEx function



## -description
A protocol driver calls the 
  <b>NdisCompleteBindAdapterEx</b> function to complete a binding operation for which the driver's 
  <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function
  returned NDIS_STATUS_PENDING.



## -syntax

````
VOID NdisCompleteBindAdapterEx(
  _In_ NDIS_HANDLE BindContext,
  _In_ NDIS_STATUS Status
);
````


## -parameters

### -param BindContext [in]

The handle that NDIS passed to the 
     <i>BindContext</i> parameter of the 
     <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">
     ProtocolBindAdapterEx</a> function.


### -param Status [in]

The final status of the completed bind operation. This parameter can be one of the following
     values:
     




### -param NDIS_STATUS_SUCCESS

The driver successfully completed the binding to the underlying NIC.


### -param NDIS_STATUS_XXX or NTSTATUS_XXX

The protocol driver's attempt to set up a binding failed or the protocol driver could not
       allocate the resources it needed to carry out network I/O operations. Usually, such an error status is
       propagated from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.

</dd>
</dl>

## -returns
None


## -remarks
If a protocol driver returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function,
    that driver must call 
    <b>NdisCompleteBindAdapterEx</b> after the binding operation is completed.

If the open operation was successful, the protocol driver is ready to accept receive indications from
    underlying drivers and to initiate send requests and OID requests on the binding. If the driver calls 
    <b>NdisCompleteBindAdapterEx</b> with an error status, the binding attempt failed and the driver has
    released any resources it allocated to establish the binding.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547996">Irql_Protocol_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCompleteBindAdapterEx function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

