---
UID : NC:wdm.DRIVER_LIST_CONTROL
title : DRIVER_LIST_CONTROL
author : windows-driver-content
description : The AdapterListControl routine starts a direct memory access (DMA) scatter/gather operation.
old-location : kernel\adapterlistcontrol.htm
old-project : kernel
ms.assetid : 9fb49710-5d8c-4376-9898-7f0ae570ee94
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.adapterlistcontrol, AdapterListControl, AdapterListControl routine [Kernel-Mode Driver Architecture], AdapterListControl, DRIVER_LIST_CONTROL, DRIVER_LIST_CONTROL, wdm/AdapterListControl, DrvrRtns_feb5903f-df38-4471-ab1e-2e6341620774.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Called at DISPATCH_LEVEL.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
---


# DRIVER_LIST_CONTROL function
The <i>AdapterListControl</i> routine starts a direct memory access (DMA) scatter/gather operation.

## Syntax

```
DRIVER_LIST_CONTROL DriverListControl;

_IRQL_requires_same_ VOID DriverListControl(
  _DEVICE_OBJECT * DeviceObject,
  _IRP * Irp,
  PSCATTER_GATHER_LIST ScatterGather,
  PVOID Context
)
{...}
```

## Parameters

`DeviceObject`

Caller-supplied pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

`Irp`

Caller-supplied pointer to an <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure that describes the I/O operation, if the driver has a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine. Otherwise, not used.

`ScatterGather`

Caller-supplied pointer to a <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure describing scatter/gather regions.

`Context`

Caller-supplied pointer to driver-defined context information, specified in a previous call to <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>.


## Return Value

None

## Remarks

To register an <i>AdapterListControl</i> routine for a specific device object, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> to obtain an adapter object, then call <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a> to request use of the adapter and to supply the <i>AdapterListControl</i> routine's address. When the adapter is free, the system calls the <i>AdapterListControl</i> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Called at DISPATCH_LEVEL. |
| **DDI compliance rules** |  |