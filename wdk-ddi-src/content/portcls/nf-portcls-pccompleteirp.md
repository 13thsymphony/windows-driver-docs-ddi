---
UID: NF:portcls.PcCompleteIrp
title: PcCompleteIrp function
author: windows-driver-content
description: The PcCompleteIrp function completes an IRP that was previously marked as pending.
old-location: audio\pccompleteirp.htm
old-project: audio
ms.assetid: fa0b36bf-0628-4136-9ca7-1d20823969ff
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcCompleteIrp, PcCompleteIrp function [Audio Devices], audio.pccompleteirp, audpc-routines_f61145f8-9e55-4b2a-a3aa-37f7be4f4df3.xml, portcls/PcCompleteIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcCompleteIrp function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
-	PcCompleteIrp
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcCompleteIrp function
The <b>PcCompleteIrp</b> function completes an IRP that was previously marked as pending.

## Syntax

```
PORTCLASSAPI NTSTATUS PcCompleteIrp(
  PDEVICE_OBJECT pDeviceObject,
  PIRP           pIrp,
  NTSTATUS       ntStatus
);
```

## Parameters

`pDeviceObject`

Pointer to the device object for the device. This parameter must point to a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.

`pIrp`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> that is to be completed

`ntStatus`

Specifies the status of the completed IRP. See the list of NTSTATUS values defined in header file ntstatus.h.


## Return Value

<b>PcCompleteIrp</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## Remarks

<b>PcCompleteIrp</b> is used when an IRP handler returns STATUS_PENDING and the IRP must later be completed. When the adapter driver finishes all processing of the IRP, it calls <b>PcCompleteIrp</b> to complete the IRP.

The IRP handler should not call this function. An adapter driver's IRP handler instead calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff537691">PcDispatchIrp</a> to pass the IRP to the PortCls system driver's IRP handler to perform all remaining processing of the IRP.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcCompleteIrp function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537691">PcDispatchIrp</a>