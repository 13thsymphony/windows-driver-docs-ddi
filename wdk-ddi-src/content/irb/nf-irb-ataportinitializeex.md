---
UID: NF:irb.AtaPortInitializeEx
title: AtaPortInitializeEx function
author: windows-driver-content
description: The AtaPortInitializeEx ATA port driver library routine initializes the port and miniport drivers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportinitializeex.htm
old-project: storage
ms.assetid: 578992cf-63eb-4b8e-b0cb-9caee5c534e1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortInitializeEx, AtaPortInitializeEx routine [Storage Devices], atartns_dab74a62-5788-4de9-91eb-e1eb7a7bcaf5.xml, irb/AtaPortInitializeEx, storage.ataportinitializeex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
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
req.lib: Pciidex.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Pciidex.lib
-	Pciidex.dll
api_name:
-	AtaPortInitializeEx
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortInitializeEx function
The <b>AtaPortInitializeEx</b> ATA port driver library routine initializes the port and miniport drivers.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
_IRQL_requires_same_ ULONG AtaPortInitializeEx(
  PVOID                     DriverObject,
  PVOID                     RegistryPath,
  PIDE_CONTROLLER_INTERFACE ControllerInterface
);
```

## Parameters

`DriverObject`

A pointer to the miniport driver object.

`RegistryPath`

Contains a Unicode string that indicates the location in the registry where the miniport driver configuration information is stored.

`ControllerInterface`

Contains the entry points for the <b><i>AtaAdapterControl</i></b>, <b><i>AtaChannelInitRoutine</i></b>, <b><i>AtaControllerChannelEnabled</i></b>, and <b><i>AtaControllerTransferModeSelect</i></b> routines.


## Return Value

<b>AtaPortInitializeEx</b> returns STATUS_SUCCESS if the operation succeeds.  Otherwise, it returns an error code.

## Remarks

The <b>AtaPortInitializeEx</b> routine initializes key data structures that are used by the port and miniport drivers. It also starts the initialization of the controller's channels. The following sequence describes the principal actions taken by this routine:

<ol>
<li>While in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, the miniport driver calls the port driver's <b>AtaPortInitializeEx</b> library routine and passes it the following key parameters: <ul>
<li><i>ControllerInterface</i>: Contains the entry points for the <b><i>AtaAdapterControl</i></b>, <b><i>AtaChannelInitRoutine</i></b>, <b><i>AtaControllerChannelEnabled</i></b>, and <b><i>AtaControllerTransferModeSelect</i></b> routines.</li>
</ul>
</li>
<li>The <b>AtaPortInitializeEx</b> routine initializes key data structures that are used by the port and miniport drivers and performs the following actions:<ol>
<li>Initializes the miniport driver's dispatch tables.</li>
<li>Allocates an extension for the driver object. </li>
<li>Copies ControllerInterface into the driver extension.</li>
<li>After <b><i>AtaPortInitializeEx</i></b> completes the initialization of the port driver, it returns to the miniport driver's <b><i>DriverEntry</i></b> routine.</li>
</ol>
</li>
<li>
While starting the adapter device, the miniport driver routine <b><i>AtaAdapterControl</i></b> will be called by the port driver with control action <b>IdeStart</b>.

</li>
<li>
When the ATA port driver is processing a channel device start request, the miniport driver routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a> is called for each channel on the controller to determine whether it is enabled.

</li>
<li>
After the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a> routine determines which channels are enabled, the ATA port driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a> for this channel. 

</li>
</ol>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Pciidex.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559036">IDE_CONTROLLER_CONFIGURATION</a>