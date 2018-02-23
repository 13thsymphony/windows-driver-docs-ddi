---
UID: NS:pepfx._PEP_ACPI_PREPARE_DEVICE
title: "_PEP_ACPI_PREPARE_DEVICE"
author: windows-driver-content
description: The PEP_ACPI_PREPARE_DEVICE structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.
old-location: kernel\pep_acpi_prepare_device.htm
old-project: kernel
ms.assetid: F8D6680D-EFA7-4DED-B808-0E738A852641
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPEP_ACPI_PREPARE_DEVICE structure pointer [Kernel-Mode Driver Architecture], *PPEP_ACPI_PREPARE_DEVICE, PEP_ACPI_PREPARE_DEVICE, kernel.pep_acpi_prepare_device, PEP_ACPI_PREPARE_DEVICE structure [Kernel-Mode Driver Architecture], _PEP_ACPI_PREPARE_DEVICE, PPEP_ACPI_PREPARE_DEVICE, pepfx/PPEP_ACPI_PREPARE_DEVICE, pepfx/PEP_ACPI_PREPARE_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_PREPARE_DEVICE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_PREPARE_DEVICE, *PPEP_ACPI_PREPARE_DEVICE
---

# _PEP_ACPI_PREPARE_DEVICE structure
The <b>PEP_ACPI_PREPARE_DEVICE</b> structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.

## Syntax
````
typedef struct _PEP_ACPI_PREPARE_DEVICE {
  PANSI_STRING AcpiDeviceName;
  ULONG        InputFlags;
  BOOLEAN      DeviceAccepted;
  ULONG        OutputFlags;
} PEP_ACPI_PREPARE_DEVICE, *PPEP_ACPI_PREPARE_DEVICE;
````

## Members


`AcpiDeviceName`

[in] A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure that contains the fully qualified BIOS name for the device. This name specifies the path and name of the device in the ACPI namespace. For more information, see <a href="https://msdn.microsoft.com/fe0553df-a5b9-46c4-8e1d-8b89a7d4ad67">Enumerating Child Devices and Control Methods</a>.

`DeviceAccepted`

[out] Whether the PEP is prepared to provide ACPI services for the device. Set this member to TRUE if the PEP is prepared to be the sole provider of ACPI services for this device, and to FALSE if it is not.

`InputFlags`

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_PREPARE_DEVICE_INPUT_FLAG_NONE (0x0).

`OutputFlags`

[out] A set of output flags. No flags are currently defined for this member. Set this member to PEP_ACPI_PREPARE_DEVICE_OUTPUT_FLAG_NONE (0x0).

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186686">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a> notification. The <b>AcpiDeviceName</b> and <b>InputFlags</b> members of the structure contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>DeviceAccepted</b> and <b>OutputFlags</b> members contain output values that the PEP writes to the structure in response to the notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186686">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_PREPARE_DEVICE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>