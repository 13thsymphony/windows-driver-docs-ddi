---
UID: NC:ntddk.DRIVER_REINITIALIZE
title: DRIVER_REINITIALIZE
author: windows-driver-content
description: The Reinitialize routine continues driver and device initialization after the driver's DriverEntry routine returns.
old-location: kernel\reinitialize.htm
old-project: kernel
ms.assetid: 5e883b80-a6e6-44b4-9e1c-78402b91edb9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.reinitialize, Reinitialize routine [Kernel-Mode Driver Architecture], Reinitialize, DRIVER_REINITIALIZE, DRIVER_REINITIALIZE, ntddk/Reinitialize, DrvrRtns_193becfd-0e72-48f0-b6da-b916851c31a4.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ntddk.h
apiname:
-	Reinitialize
product: Windows
targetos: Windows
req.typenames: "*PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA"
---


# DRIVER_REINITIALIZE callback function
The <i>Reinitialize</i> routine continues driver and device initialization after the driver's <b>DriverEntry</b> routine returns.

## Syntax

```
DRIVER_REINITIALIZE DriverReinitialize;

void DriverReinitialize(
  _DRIVER_OBJECT *DriverObject,
  PVOID Context,
  ULONG Count
)
{...}
```

## Parameters

`*DriverObject`

Caller-supplied pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure. This is the driver's driver object.

`Context`

Caller-supplied pointer to context information, specified in a previous call to <a href="..\ntddk\nf-ntddk-ioregisterdriverreinitialization.md">IoRegisterDriverReinitialization</a> or <a href="..\ntddk\nf-ntddk-ioregisterbootdriverreinitialization.md">IoRegisterBootDriverReinitialization</a>.

`Count`

Caller-supplied value representing the number of times the <i>Reinitialize</i> routine has been called, including the current call.


## Return Value

None

## Remarks

To queue a <i>Reinitialize</i> routine for execution, a driver's <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine must call either <a href="..\ntddk\nf-ntddk-ioregisterdriverreinitialization.md">IoRegisterDriverReinitialization</a> or <a href="..\ntddk\nf-ntddk-ioregisterbootdriverreinitialization.md">IoRegisterBootDriverReinitialization</a>. The <i>Reinitialize</i> routine can also call <b>IoRegisterDriverReinitialization</b> itself, which causes the routine to be requeued. This requeuing can occur multiple times, and the routine's <i>Count</i> parameter indicates the number of times it has been called. The first call to <b>IoRegisterDriverReinitialization</b> must be made from <b>DriverEntry</b>, and <b>DriverEntry</b> must return STATUS_SUCCESS.

For more information about implementing a <i>Reinitialize</i> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566403">Writing a Reinitialize Routine</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **IRQL** | Called at PASSIVE_LEVEL. |