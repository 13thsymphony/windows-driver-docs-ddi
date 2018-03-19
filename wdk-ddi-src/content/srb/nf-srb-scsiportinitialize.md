---
UID: NF:srb.ScsiPortInitialize
title: ScsiPortInitialize function
author: windows-driver-content
description: For a non-Plug and Play miniport driver, the ScsiPortInitialize routine sets up the PORT_CONFIGURATION_INFORMATION structure and calls the miniport driver's HwScsiFindAdapter routine.
old-location: storage\scsiportinitialize.htm
old-project: storage
ms.assetid: f6adca68-e016-4725-bd8e-691c71d1d471
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortInitialize, ScsiPortInitialize routine [Storage Devices], scsiprt_62fb91f9-a420-4156-9a1e-b58b65067a8b.xml, srb/ScsiPortInitialize, storage.scsiportinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Scsiport.lib
-	Scsiport.dll
api_name:
-	ScsiPortInitialize
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortInitialize function
For a non-Plug and Play miniport driver, the <b>ScsiPortInitialize</b> routine sets up the PORT_CONFIGURATION_INFORMATION structure and calls the miniport driver's <a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a> routine. <b>ScsiPortInitialize</b> also sets up system objects and resources on behalf of miniport drivers. For a Plug and Play miniport driver, <b>ScsiPortInitialize</b> stores the miniport driver's initialization data for future use. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
ULONG ScsiPortInitialize(
  _In_ PVOID                          Argument1,
  _In_ PVOID                          Argument2,
  _In_ struct _HW_INITIALIZATION_DATA *HwInitializationData,
  _In_ PVOID                          HwContext
);
````

## Parameters

`Argument1`

Pointer to the driver object that the operating system passed to the miniport driver in the first argument of its <b>DriverEntry</b> routine.

`Argument2`

Pointer to some context information that the operating system passed to the miniport driver in the second argument of its <b>DriverEntry</b>.

`HwInitializationData`

Pointer to the initialization and configuration information supplied by <b>DriverEntry</b>.

`HwContext`

Specifies the address of a context value to be passed to the miniport driver's <a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a> routine. Only legacy miniport drivers that scan the bus for HBAs rather than receiving configuration information from the port driver can use this parameter to store state between calls to <i>HwScsiFindAdapter</i>.


## Return Value

<b>ScsiPortInitialize</b> returns a status value that is used as the return value from the miniport driver's <b>DriverEntry</b> routine.

## Remarks

Every miniport driver's <b>DriverEntry</b> routine must call <b>ScsiPortInitialize</b> after the miniport driver has first zeroed and then set up the HW_INITIALIZATION_DATA.

If a miniport driver can support HBAs on different types of I/O buses, such as both <b>Isa</b> and <b>MicroChannel</b> type I/O buses, the miniport driver should call <b>ScsiPortInitialize</b> for each supported interface type.

A miniport driver that calls <b>ScsiPortInitialize</b> more than once should check the value returned by <b>ScsiPortInitialize</b> at each call and save the lowest value for all its calls. The <b>DriverEntry</b> routine must return the lowest value when it returns control to the system. Miniport driver writers can make no assumptions about the values returned by <b>ScsiPortInitialize</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a>



<a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552654">DriverEntry of SCSI Miniport Driver</a>