---
UID: NC:srb.PHW_STARTIO
title: PHW_STARTIO
author: windows-driver-content
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_startio.htm
old-project: storage
ms.assetid: 1b177ef5-2b58-425e-9b9a-428bbe15de69
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "(*PHW_STARTIO), (*PHW_STARTIO) callback function [Storage Devices], ide_minikr_16fd699a-4cb9-4741-9e50-3fa8177f49f2.xml, srb/(*PHW_STARTIO), storage.phw_startio"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
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
-	srb.h
api_name:
-	(*PHW_STARTIO)
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---


# PHW_STARTIO callback function
The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.

## Syntax

```
PHW_STARTIO PhwStartio;

BOOLEAN PhwStartio(
  PVOID DeviceExtension,
  PSCSI_REQUEST_BLOCK Srb
)
{...}
```

## Parameters

`DeviceExtension`

Pointer to the miniport driver's per-HBA storage area.

`Srb`

Pointer to the SCSI request block to be started.


## Return Value

The start I/O routine returns <b>TRUE</b> to acknowledge receipt of the SCSI request block (SRB). If the start I/O routine does not receive a well-formed SRB, it returns <b>FALSE</b>.

## Remarks

The start routine for both SCSI and StorPort miniport drivers are declared using this prototype. 

For more information about the SCSI miniport driver's start I/O routine see <a href="..\srb\nc-srb-phw_startio.md">HwScsiStartIo</a>. 

For more information about the miniport driver's start I/O routine that is used with the StorPort driver see <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Storport.h, Srb.h, Storport.h) |

## See Also

<a href="..\srb\nc-srb-phw_startio.md">HwScsiStartIo</a>



<a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>