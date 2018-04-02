---
UID: NS:ucxcontroller._UCX_CONTROLLER_ACPI_INFORMATION
title: "_UCX_CONTROLLER_ACPI_INFORMATION"
author: windows-driver-content
description: This structure provides information about an advanced Configuration and power interface (ACPI) USB controller.
old-location: buses\_ucx_controller_acpi_information.htm
old-project: usbref
ms.assetid: BB5C69FF-166A-4A38-BF5E-FD644FCD1285
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUCX_CONTROLLER_ACPI_INFORMATION, P_UCX_CONTROLLER_ACPI_INFORMATION, P_UCX_CONTROLLER_ACPI_INFORMATION structure pointer [Buses], UCX_CONTROLLER_ACPI_INFORMATION, UCX_CONTROLLER_ACPI_INFORMATION structure [Buses], _UCX_CONTROLLER_ACPI_INFORMATION, buses._ucx_controller_acpi_information, ucxcontroller/P_UCX_CONTROLLER_ACPI_INFORMATION, ucxcontroller/_UCX_CONTROLLER_ACPI_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	Ucxcontroller.h
api_name:
-	UCX_CONTROLLER_ACPI_INFORMATION
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_ACPI_INFORMATION, *PUCX_CONTROLLER_ACPI_INFORMATION
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_ACPI_INFORMATION structure
This structure provides information about an advanced Configuration and power interface (ACPI) USB controller.

## Syntax
```
typedef struct _UCX_CONTROLLER_ACPI_INFORMATION {
  CHAR VendorId[MAX_VENDOR_ID_STRING_LENGTH];
  CHAR DeviceId[MAX_DEVICE_ID_STRING_LENGTH];
  CHAR RevisionId[MAX_REVISION_ID_STRING_LENGTH];
} *PUCX_CONTROLLER_ACPI_INFORMATION, UCX_CONTROLLER_ACPI_INFORMATION;
```

## Members


`VendorId`

The vendor ID of the ACPI USB controller.

`DeviceId`

The device ID of the ACPI USB controller.

`RevisionId`

The revision ID of the ACPI USB controller.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxcontroller.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188058">UCX_CONTROLLER_CONFIG_SET_ACPI_INFO</a>