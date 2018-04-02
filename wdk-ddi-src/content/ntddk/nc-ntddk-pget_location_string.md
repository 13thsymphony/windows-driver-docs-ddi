---
UID: NC:ntddk.PGET_LOCATION_STRING
title: PGET_LOCATION_STRING
author: windows-driver-content
description: The PnpGetLocationString routine provides the device-specific part of the device's SPDRP_LOCATION_PATHS property.
old-location: kernel\pnpgetlocationstring.htm
old-project: kernel
ms.assetid: 03ebdeed-10f0-4633-a9cd-4db683a8c3a7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PGET_LOCATION_STRING, PnpGetLocationString, PnpGetLocationString routine [Kernel-Mode Driver Architecture], drvr_interface_86bd2a9c-408f-430f-9ab7-5c368600de1e.xml, kernel.pnpgetlocationstring, ntddk/PnpGetLocationString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Server 2003.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	PnpGetLocationString
product:
- Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---


# PGET_LOCATION_STRING callback function
The <i>PnpGetLocationString</i> routine provides the device-specific part of the device's SPDRP_LOCATION_PATHS property.

## Syntax

```
PGET_LOCATION_STRING PgetLocationString;

NTSTATUS PgetLocationString(
  PVOID Context,
  PZZWSTR *LocationStrings
)
{...}
```

## Parameters

`Context`

A pointer to interface-specific context information.  The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559634">PNP_LOCATION_INTERFACE</a> structure.

`*LocationStrings`

A pointer to a sequence of null-terminated Unicode strings, that is terminated by another zero. Each string serves as a location string for the device. Drivers typically return a single string.


## Return Value

The routine returns an NTSTATUS value to indicate the status of the operation.

## Remarks

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff559634">PNP_LOCATION_INTERFACE</a> structure supplies a pointer to the <i>PnpGetLocationString</i> routine.

The <i>PnpGetLocationString</i> routine provides the device-specific part of the location string for the device.  The Plug and Play (PnP) manager assembles the location string for a device by querying the driver for the device, for the device's bus, and any parent buses, and concatenating the provided strings together.

The routine must return a string that is unique to the device relative to its bus. The string must be the same for the device across all versions of the operating system. Once you select a string for this purpose, you must not change it.

By convention, the location string takes the form <i>ServiceName(BusSpecificLocation)</i>. For example, PCI devices use PCI(<i>XXYY</i>), where <i>XX</i> is the device number, and <i>YY</i> is the function number.

The <i>PnpGetLocationString</i> routine calls a routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> to allocate the memory for the location string. The caller is responsible for calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> routine to free the memory pointed to by <i>LocationStrings</i> when the location string is no longer needed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Server 2003.  |
| **Target Platform** | Desktop |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **IRQL** | "<= PASSIVE_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559634">PNP_LOCATION_INTERFACE</a>