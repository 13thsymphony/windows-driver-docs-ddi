---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_ABORT_OPERATION
title: UFX_PROPRIETARY_CHARGER_ABORT_OPERATION
author: windows-driver-content
description: The filter driver's implementation to abort a charger operation.
old-location: buses\ufx_proprietary_charger_abort_operation.htm
old-project: usbref
ms.assetid: 32BCBE1C-BD0E-46D6-9C6D-6B8F1CE0E540
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFN_UFX_PROPRIETARY_CHARGER_ABORT_OPERATION, PFN_UFX_PROPRIETARY_CHARGER_ABORT_OPERATION callback function pointer [Buses], UFX_PROPRIETARY_CHARGER_ABORT_OPERATION, UfxProprietaryChargerAbort, UfxProprietaryChargerAbort callback function [Buses], buses.ufx_proprietary_charger_abort_operation, ufxproprietarycharger/UfxProprietaryChargerAbort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ufxproprietarycharger.h
api_name:
-	PFN_UFX_PROPRIETARY_CHARGER_ABORT_OPERATION
product: Windows
targetos: Windows
req.typenames: UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS
req.product: Windows 10 or later.
---


# UFX_PROPRIETARY_CHARGER_ABORT_OPERATION callback function
The filter driver's implementation to abort a charger operation.

## Syntax

```
UFX_PROPRIETARY_CHARGER_ABORT_OPERATION UfxProprietaryChargerAbortOperation;

NTSTATUS UfxProprietaryChargerAbortOperation(
  PVOID Context
)
{...}
```

## Parameters

`Context`

A pointer to a driver-defined context.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks

To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ufxproprietarycharger.h |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>