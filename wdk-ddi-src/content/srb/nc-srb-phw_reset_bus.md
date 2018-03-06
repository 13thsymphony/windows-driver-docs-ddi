---
UID: NC:srb.PHW_RESET_BUS
title: PHW_RESET_BUS
author: windows-driver-content
description: The PHW_RESET_BUS prototype declares a routine that resets the indicated SCSI bus.
old-location: storage\phw_reset_bus.htm
old-project: storage
ms.assetid: 8c41ca6d-4b55-4858-b8bb-d7b2e682a8f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "(*PHW_RESET_BUS), (*PHW_RESET_BUS) callback function [Storage Devices], ide_minikr_6cda3e23-0fa6-48dd-a0c0-3d47287eb829.xml, srb/(*PHW_RESET_BUS), storage.phw_reset_bus"
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
-	(*PHW_RESET_BUS)
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---


# PHW_RESET_BUS callback function
The PHW_RESET_BUS prototype declares a routine that resets the indicated SCSI bus.

## Syntax

```
PHW_RESET_BUS PhwResetBus;

BOOLEAN PhwResetBus(
  PVOID DeviceExtension,
  ULONG PathId
)
{...}
```

## Parameters

`DeviceExtension`

Pointer to the miniport driver's per-HBA storage area.

`PathId`

Contains a number that identifies the SCSI bus to be reset.


## Return Value

The routine that this prototype declares returns <b>TRUE</b> if the bus is successfully reset. The routine returns <b>FALSE</b> if the bus is not successfully reset.

## Remarks

The initialization routine for both SCSI and StorPort miniport drivers are declared using this prototype. 

For more information about the SCSI miniport driver's bus reset routine see <a href="..\srb\nc-srb-phw_reset_bus.md">HwScsiResetBus</a>. 

For more information about the bus reset routine that is used with the StorPort driver's miniport driver routine, see <a href="..\storport\nc-storport-hw_reset_bus.md">HwStorResetBus</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Storport.h, Srb.h, Storport.h) |

## See Also

<a href="..\storport\nc-storport-hw_reset_bus.md">HwStorResetBus</a>



<a href="..\srb\nc-srb-phw_reset_bus.md">HwScsiResetBus</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_RESET_BUS callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>