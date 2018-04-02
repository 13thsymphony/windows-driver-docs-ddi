---
UID: NF:portcls.PcCompletePendingPropertyRequest
title: PcCompletePendingPropertyRequest function
author: windows-driver-content
description: The PcCompletePendingPropertyRequest function is called to complete a pending property request.
old-location: audio\pccompletependingpropertyrequest.htm
old-project: audio
ms.assetid: a4b59403-9a2f-4857-947b-dff8e3ea079c
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcCompletePendingPropertyRequest, PcCompletePendingPropertyRequest function [Audio Devices], audio.pccompletependingpropertyrequest, audpc-routines_934503ea-325f-4e57-ba45-e8834a64cefa.xml, portcls/PcCompletePendingPropertyRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcCompletePendingPropertyRequest function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcCompletePendingPropertyRequest
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcCompletePendingPropertyRequest function
The <b>PcCompletePendingPropertyRequest</b> function is called to complete a pending property request.

## Syntax

```
PORTCLASSAPI NTSTATUS PcCompletePendingPropertyRequest(
  PPCPROPERTY_REQUEST PropertyRequest,
  NTSTATUS            NtStatus
);
```

## Parameters

`PropertyRequest`

Pointer to the property request that was passed to the property handler. The request is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537723">PCPROPERTY_REQUEST</a>.

`NtStatus`

Specifies the completion status of the request. See the list of NTSTATUS values defined in header file ntstatus.h.


## Return Value

<b>PcCompletePendingPropertyRequest</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## Remarks

If a miniport driver returns STATUS_PENDING from a property handler, it is obliged to keep a pointer to the property-request structure and to complete the request at some later time by calling this function.

The driver should call <b>PcCompletePendingPropertyRequest</b> only when the request is no longer pending. Never call this function with an <i>NtStatus</i> value of STATUS_PENDING.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcCompletePendingPropertyRequest function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537723">PCPROPERTY_REQUEST</a>