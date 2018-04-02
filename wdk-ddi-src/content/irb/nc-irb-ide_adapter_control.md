---
UID: NC:irb.IDE_ADAPTER_CONTROL
title: IDE_ADAPTER_CONTROL
author: windows-driver-content
description: The AtaAdapterControl miniport driver routine is called to perform Plug and Play (PnP) and Power Management operations on the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataadaptercontrol.htm
old-project: storage
ms.assetid: 50125022-7450-4582-b98d-1d597e4e96d4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaAdapterControl, AtaAdapterControl routine [Storage Devices], IDE_ADAPTER_CONTROL, atartns_6460976d-3415-4cda-b128-f74baefd075f.xml, irb/AtaAdapterControl, storage.ataadaptercontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: irb.h
req.include-header: Irb.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	irb.h
api_name:
-	AtaAdapterControl
product: Windows
targetos: Windows
req.typenames: IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS, IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
---


# IDE_ADAPTER_CONTROL callback function
The <i>AtaAdapterControl</i> miniport driver routine is called to perform Plug and Play (PnP) and Power Management operations on the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
IDE_ADAPTER_CONTROL IdeAdapterControl;

BOOLEAN IdeAdapterControl(
  PVOID ControllerExtension,
  IDE_CONTROL_ACTION ControlAction,
  PVOID Parameters
)
{...}
```

## Parameters

`ControllerExtension`

A pointer to the controller extension.

`ControlAction`

One of five actions that the miniport driver must perform as defined in the following table.
  

<table>
<tr>
<th>ControlAction</th>
<th>Parameters</th>
<th>Description</th>
</tr>
<tr>
<td>
IdeStart

</td>
<td>
IDE_CONTROLLER_CONFIGURATION

</td>
<td>
Indicates that the adapter is being started. The miniport driver should update the member in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559036">IDE_CONTROLLER_CONFIGURATION</a> structure. If it is required, the miniport driver could obtain its hardware resources from the <b>IDE_CONTROLLER_CONFIGURATION</b> structure.

</td>
</tr>
<tr>
<td>
IdeStop

</td>
<td>
None

</td>
<td>
The miniport driver should stop using any resources that are allocated for this controller. Be aware that the port driver guarantees that all the channels that  are exposed by the adapter are stopped before it stops the adapter.

</td>
</tr>
<tr>
<td>
IdePowerUp

</td>
<td>
None

</td>
<td>
Indicates that the adapter is being turned on. Anything that does not persist across a power cycle must be configured during IdePowerUp.  

</td>
</tr>
<tr>
<td>
IdePowerDown

</td>
<td>
None

</td>
<td>
Indicates that the adapter is being turned off.

</td>
</tr>
<tr>
<td>
IdeVendorDefined

</td>
<td>
None

</td>
<td>
Indicates that the miniport driver should perform a vendor-defined control action..

</td>
</tr>
</table>

`Parameters`

Parameters associated with the given action.


## Return Value

The miniport driver must return <b>TRUE</b> to acknowledge the completion of the requested action. A return value of <b>FALSE</b> indicates that the miniport driver was unable to complete the action successfully. A return value of <b>FALSE</b> for certain actions might cause the device installation to fail.

## Remarks

The port driver guarantees that there is no outstanding I/O on the adapter before it invokes the <i>AtaAdapterControl</i> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Irb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559036">IDE_CONTROLLER_CONFIGURATION</a>