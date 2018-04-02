---
UID: NF:ndis.NdisMCmRegisterSapComplete
title: NdisMCmRegisterSapComplete macro
author: windows-driver-content
description: NdisMCmRegisterSapComplete returns the final status of a client's request, for which the MCM driver's ProtocolCmRegisterSap function previously returned NDIS_STATUS_PENDING, to register a SAP.
old-location: netvista\ndismcmregistersapcomplete.htm
old-project: netvista
ms.assetid: 53f94e25-ca6c-4230-8447-d36774322dc7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMCmRegisterSapComplete, NdisMCmRegisterSapComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_4b7dfebf-1828-41cd-9645-0fc6774cc9a8.xml, ndis/NdisMCmRegisterSapComplete, netvista.ndismcmregistersapcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmRegisterSapComplete
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCmRegisterSapComplete function
<b>NdisMCmRegisterSapComplete</b> returns the final status of a client's request, for which the MCM driver's
  
  <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a> function
  previously returned NDIS_STATUS_PENDING, to register a SAP.

## Syntax

```
void NdisMCmRegisterSapComplete(
   _S_,
   _H_,
   _C_
);
```

## Parameters

`_S_`

TBD

`_H_`

TBD

`_C_`

TBD


## Return Value

None

## Remarks

An MCM driver must call 
    <b>NdisMCmRegisterSapComplete</b> if its 
    <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a> function
    returned NDIS_STATUS_PENDING when it was called with the given 
    <i>NdisSapHandle</i> . The call to 
    <b>NdisMCmRegisterSapComplete</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/b0a2a224-3353-4f20-b14f-ed5d633a6ead">
    ProtocolClRegisterSapComplete</a> function.

If the MCM driver sets 
    <i>Status</i> to anything other than NDIS_STATUS_SUCCESS, it should consider the 
    <i>NdisSapHandle</i> invalid when 
    <b>NdisMCmRegisterSapComplete</b> returns control. After failing a SAP registration, the CM can release or
    reuse the per-SAP context area, if any, that it already allocated. NDIS also releases its context for the
    SAP if the MCM driver fails the registration.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmRegisterSapComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmRegisterSapComplete</b> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_MCM_Function |

## See Also

<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561689">NdisCmRegisterSapComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562830">NdisMCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/b0a2a224-3353-4f20-b14f-ed5d633a6ead">
   ProtocolClRegisterSapComplete</a>



<a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a>