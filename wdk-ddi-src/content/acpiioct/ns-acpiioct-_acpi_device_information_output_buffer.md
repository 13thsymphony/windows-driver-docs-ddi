---
UID: NS:acpiioct._ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER
title: "_ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER"
author: windows-driver-content
description: The ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure contains output arguments from the IOCTL_ACPI_GET_DEVICE_INFORMATION control method.
old-location: acpi\acpi_device_information_output_buffer.htm
old-project: acpi
ms.assetid: 15AA7E06-DD7F-46B4-B2C2-604EA5150F7D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_DEVICE_INFORMATION_OUTPUT_BUFFER, ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER, ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure [ACPI Devices], PACPI_DEVICE_INFORMATION_OUTPUT_BUFFER, PACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure pointer [ACPI Devices], _ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER, acpi.acpi_device_information_output_buffer, acpi.acpi_get_device_information_output_buffer, acpiioct/ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER, acpiioct/PACPI_DEVICE_INFORMATION_OUTPUT_BUFFER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8 and later versions of Windows.
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
-	Acpiioct.h
api_name:
-	ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER
product:
- Windows
targetos: Windows
req.typenames: ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER, *PACPI_DEVICE_INFORMATION_OUTPUT_BUFFER
---

# _ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure
The ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure contains output arguments from the IOCTL_ACPI_GET_DEVICE_INFORMATION control method.

## Syntax
```
typedef struct _ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER {
  ULONG  Signature;
  USHORT Size;
  UCHAR  Revision;
  UCHAR  Reserved0;
  USHORT VendorIdStringOffset;
  USHORT VendorStringLength;
  USHORT DeviceIdStringOffset;
  USHORT SubSystemIdStringOffset;
  USHORT SubSystemStringLength;
  USHORT SubDeviceIdStringOffset;
  USHORT InstanceIdLength;
  USHORT InstanceIdOffset;
  USHORT BaseClassCode;
  USHORT HardwareRevision;
  UCHAR  ProgrammingInterface;
  UCHAR  Reserved1;
  USHORT SubClassCode;
} ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER, *PACPI_DEVICE_INFORMATION_OUTPUT_BUFFER;
```

## Members


`Signature`

A unique identifier for the IOCTL that returns this buffer. Used for verification.

`Size`

The size, in bytes, of the ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure.

`Revision`

Revision of the ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure.

`Reserved0`

Reserved. Do not use.

`VendorIdStringOffset`

The offset from the beginning of this structure to the beginning of the <b>VendorIDString</b> member. This string uniquely identifies The manufacturer and the device itself.

`VendorStringLength`

The length of the <b>VendorIDString</b> member.

`DeviceIdStringOffset`

The offset from the beginning of this structure to the beginning of the <b>DeviceIDString</b> member. This string uniquely identifies the device.

`SubSystemIdStringOffset`

The offset from the beginning of this structure to the beginning of the <b>SubSystemIDString</b> member. This string uniquely identifies the manufacturer and the subsystem (chip or board) into which the device is integrated.

`SubSystemStringLength`

The length of the <b>SubSystemIDString</b> member.

`SubDeviceIdStringOffset`

The offset from the beginning of this structure to the beginning of the <b>DeviceIDString</b> member. This string uniquely identifies the subsystem.

`InstanceIdLength`

The length of the <b>InstanceIDString</b> member.

`InstanceIdOffset`

The offset from the beginning of this structure to the beginning of the <b>InstanceIDString</b> member. This string uniquely identifies the device amongst all such devices on the platform.

`BaseClassCode`

A number identifying the class of the device. See http://pcisig.org for baseclass code definitions.

`HardwareRevision`

A number identifying the hardware revision of the device.

`ProgrammingInterface`

A number identifying the programming interface of the device. See http://pcisig.org for class programming interface definitions.

`Reserved1`

Reserved. Do not use.

`SubClassCode`

A number identifying the subclass of the device. See http://pcisig.org for subclass code definitions.

## Remarks
Appended after the ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER are the SubSystemIdString, VendorIdString, and InstanceIdString strings, described as follows:

<b>BYTE[SubVendorStringLength+1] SubSystemIdString</b>

A string of <b>SubSystemStringLength</b> in length which contains the subsystem's manufacturer and subsystem identifiers.

<b>BYTE[VendorIdStringOffset+1] VendorIdString</b>

A string of <b>VendorStringLength</b> in length which contains the device's manufacturer and device identifiers.

<b>BYTE[InstanceIdOffset+1] InstanceIdString</b>

A string of <b>InstanceIDLength</b> in length which contains a number that uniquely identifies the device amongst all such devices on the platform (i.e. all devices with the same Vendor, Device, SubsystemVendor and SubsystemDevice IDs.)

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 and later versions of Windows. Windows 8 and later versions of Windows. |
| **Header** | acpiioct.h (include Acpiioct.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450790">IOCTL_ACPI_GET_DEVICE_INFORMATION</a>