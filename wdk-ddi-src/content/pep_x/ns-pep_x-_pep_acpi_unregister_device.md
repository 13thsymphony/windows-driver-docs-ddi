---
UID: NS:pep_x._PEP_ACPI_UNREGISTER_DEVICE
title: "_PEP_ACPI_UNREGISTER_DEVICE"
author: windows-driver-content
description: The PEP_ACPI_UNREGISTER_DEVICE structure contains information about a device that has been unregistered from ACPI services.
old-location: kernel\pep_acpi_unregister_device.htm
old-project: kernel
ms.assetid: AA9D9AB3-B799-4D21-A418-D29360BBE605
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_ACPI_UNREGISTER_DEVICE, PEP_ACPI_UNREGISTER_DEVICE, PEP_ACPI_UNREGISTER_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_UNREGISTER_DEVICE, PPEP_ACPI_UNREGISTER_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_UNREGISTER_DEVICE, kernel.pep_acpi_unregister_device, pepfx/PEP_ACPI_UNREGISTER_DEVICE, pepfx/PPEP_ACPI_UNREGISTER_DEVICE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_UNREGISTER_DEVICE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_UNREGISTER_DEVICE, *PPEP_ACPI_UNREGISTER_DEVICE, PEP_ACPI_UNREGISTER_DEVICE, *PPEP_ACPI_UNREGISTER_DEVICE
---

# _PEP_ACPI_UNREGISTER_DEVICE structure
The <b>PEP_ACPI_UNREGISTER_DEVICE</b> structure contains information about a device that has been unregistered from ACPI services.

## Syntax
```
typedef struct _PEP_ACPI_UNREGISTER_DEVICE {
  PEPHANDLE DeviceHandle;
  ULONG     InputFlags;
} *PPEP_ACPI_UNREGISTER_DEVICE, PEP_ACPI_UNREGISTER_DEVICE;
```

## Members


`DeviceHandle`

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.

`InputFlags`

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_UNREGISTER_DEVICE_INPUT_FLAG_NONE (0x0).

## Remarks
This structure is used by the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_NOTIFY_ACPI_UNREGISTER_DEVICE</a> notification. The <b>DeviceHandle</b> and <b>InputFlags</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> when this notification is sent.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_NOTIFY_ACPI_UNREGISTER_DEVICE</a>