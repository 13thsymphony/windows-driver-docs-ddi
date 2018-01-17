---
UID: NF:ndis.NdisCompleteUnbindAdapterEx
title: NdisCompleteUnbindAdapterEx function
author: windows-driver-content
description: A protocol driver calls the NdisCompleteUnbindAdapterEx function to complete an unbind operation for which the driver's ProtocolUnbindAdapterEx function returned NDIS_STATUS_PENDING.
old-location: netvista\ndiscompleteunbindadapterex.htm
old-project: netvista
ms.assetid: 3a1daad4-d4b7-4950-be58-73612949fba9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisCompleteUnbindAdapterEx
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
req.alt-api: NdisCompleteUnbindAdapterEx
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
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisCompleteUnbindAdapterEx function



## -description
A protocol driver calls the 
  <b>NdisCompleteUnbindAdapterEx</b> function to complete an unbind operation for which the driver's 
  <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a> function
  returned NDIS_STATUS_PENDING.



## -syntax

````
VOID NdisCompleteUnbindAdapterEx(
  _In_ NDIS_HANDLE UnbindContext
);
````


## -parameters

### -param UnbindContext [in]

The handle that NDIS passed to the 
     <i>UnbindContext</i> parameter of the 
     <i>ProtocolUnbindAdapterEx</i> function.


## -returns
None


## -remarks
When a protocol driver returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function, that driver must call 
    <b>NdisCompleteUnbindAdapterEx</b> after the unbind operation is completed.

When the driver calls 
    <b>NdisCompleteUnbindAdapterEx</b>, the driver has finished cleaning up any per-binding context
    information that the driver maintains for the binding, and released any resources that it allocated to
    establish the binding.

On return from 
    <b>NdisCompleteUnbindAdapterEx</b> the 
    <i>UnbindContext</i> handle is invalid. That is, the protocol driver should not pass this handle in calls
    to any 
    <b>Ndis<i>Xxx</i></b> function.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCompleteUnbindAdapterEx function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

