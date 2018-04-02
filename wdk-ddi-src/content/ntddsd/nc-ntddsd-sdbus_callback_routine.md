---
UID: NC:ntddsd.SDBUS_CALLBACK_ROUTINE
title: SDBUS_CALLBACK_ROUTINE
author: windows-driver-content
description: The PSDBUS_CALLBACK_ROUTINE prototype declares the Secure Digital (SD) driver callback routine that the SD bus driver uses to report device interrupts to the driver.
old-location: sd\psdbus_callback_routine.htm
old-project: SD
ms.assetid: e63ebdcc-afcd-451e-942c-0e295eb3468f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SD.psdbus_callback_routine, SDBUS_CALLBACK_ROUTINE, SdBusCallbackRoutine, SdBusCallbackRoutine callback function [Buses], ntddsd/SdBusCallbackRoutine, sd-rtns_a51040c8-723c-45ae-9e3b-15ef2baca85b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddsd.h
req.include-header: Ntddsd.h
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
-	ntddsd.h
api_name:
-	SdBusCallbackRoutine
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_MP_REQUEST, *PSTORAGE_DIAGNOSTIC_MP_REQUEST
---


# SDBUS_CALLBACK_ROUTINE callback function
The PSDBUS_CALLBACK_ROUTINE prototype declares the Secure Digital (SD) driver callback routine that the SD bus driver uses to report device interrupts to the driver.

## Syntax

```
SDBUS_CALLBACK_ROUTINE SdbusCallbackRoutine;

void SdbusCallbackRoutine(
  PVOID CallbackRoutineContext,
  ULONG InterruptType
)
{...}
```

## Parameters

`CallbackRoutineContext`

Pointer to the context information that the bus driver passes to the callback routine. The device driver supplies the bus driver with this information when it initializes the SD bus interface.

`InterruptType`

Must be set to SDBUS_INTTYPE_DEVICE.


## Return Value

None.

## Remarks

When an SD device driver initializes an instance of the SD bus interface, it loads the <b>CallbackRoutine</b> member of the <a href="https://msdn.microsoft.com/d407131e-5dda-4d50-b09a-0f937774eefb">SDBUS_INTERFACE_PARAMETERS</a> structure with a pointer to PSDBUS_CALLBACK_ROUTINE.

The bus driver calls the SD card driver's callback routine whenever the card indicates an interrupt. The callback routine must send the appropriate device commands to handle and clear the interrupt on the card. After it completes the series of I/O operations, the SD card driver should acknowledge the interrupt. For more information about how SD card drivers acknowledge interrupts, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537616">PSDBUS_ACKNOWLEDGE_INT_ROUTINE</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntddsd.h (include Ntddsd.h) |

## See Also

<a href="https://msdn.microsoft.com/d407131e-5dda-4d50-b09a-0f937774eefb">SDBUS_INTERFACE_PARAMETERS</a>