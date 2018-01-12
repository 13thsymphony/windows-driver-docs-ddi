---
UID: NF:ndis.NdisDeregisterProtocolDriver
title: NdisDeregisterProtocolDriver function
author: windows-driver-content
description: A protocol driver calls the NdisDeregisterProtocolDriver function to release the resources that NDIS allocated when the driver called the NdisRegisterProtocolDriver function.
old-location: netvista\ndisderegisterprotocoldriver.htm
old-project: netvista
ms.assetid: 792f8f89-ff2c-45d1-bb15-9fcdafd14231
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisDeregisterProtocolDriver
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
req.alt-api: NdisDeregisterProtocolDriver
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
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisDeregisterProtocolDriver function



## -description
A protocol driver calls the
  <b>NdisDeregisterProtocolDriver</b> function to release the resources that NDIS allocated when the driver
  called the 
  <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
  NdisRegisterProtocolDriver</a> function.



## -syntax

````
VOID NdisDeregisterProtocolDriver(
  _In_ NDIS_HANDLE NdisProtocolHandle
);
````


## -parameters

### -param NdisProtocolHandle [in]

The handle returned by the 
     <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
     NdisRegisterProtocolDriver</a> function.


## -returns
None


## -remarks
Registered protocol drivers typically call 
    <b>NdisDeregisterProtocolDriver</b> when the driver's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine has been called or after errors occur
    in the 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. Protocol drivers must not
    call 
    <b>NdisDeregisterProtocolDriver</b> from any entry point that NDIS calls. Calling 
    <b>NdisDeregisterProtocolDriver</b> from such an entry point could cause a deadlock.

If a protocol driver has open bindings, its call to 
    <b>NdisDeregisterProtocolDriver</b> causes NDIS to call the protocol driver's 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function once for each open binding. NDIS calls 
    <i>ProtocolUnbindAdapterEx</i> within the context of the 
    <b>NdisDeregisterProtocolDriver</b> call.

After any outstanding bindings have been closed, 
    <b>NdisDeregisterProtocolDriver</b> releases all of the resources that NDIS allocated to track bindings
    and filters for the protocol driver.


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
PASSIVE_LEVEL

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
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDeregisterProtocolDriver function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

