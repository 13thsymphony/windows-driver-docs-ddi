---
UID: NS:ntddk._WHEA_GENERIC_ERROR_DESCRIPTOR
title: "_WHEA_GENERIC_ERROR_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_GENERIC_ERROR_DESCRIPTOR structure describes a generic error source.
old-location: whea\whea_generic_error_descriptor.htm
old-project: whea
ms.assetid: a3ab6522-8706-4166-974f-1744b352f3c2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_GENERIC_ERROR_DESCRIPTOR, PWHEA_GENERIC_ERROR_DESCRIPTOR, PWHEA_GENERIC_ERROR_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_GENERIC_ERROR_DESCRIPTOR, WHEA_GENERIC_ERROR_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_GENERIC_ERROR_DESCRIPTOR, ntddk/PWHEA_GENERIC_ERROR_DESCRIPTOR, ntddk/WHEA_GENERIC_ERROR_DESCRIPTOR, whea.whea_generic_error_descriptor, whearef_f9183d24-a7ad-4328-99b3-6e23ff890d1b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
api_name:
-	WHEA_GENERIC_ERROR_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WHEA_GENERIC_ERROR_DESCRIPTOR, *PWHEA_GENERIC_ERROR_DESCRIPTOR
---

# _WHEA_GENERIC_ERROR_DESCRIPTOR structure
The WHEA_GENERIC_ERROR_DESCRIPTOR structure describes a generic error source.

## Syntax
```
typedef struct _WHEA_GENERIC_ERROR_DESCRIPTOR {
  USHORT                       Type;
  UCHAR                        Reserved;
  UCHAR                        Enabled;
  ULONG                        ErrStatusBlockLength;
  ULONG                        RelatedErrorSourceId;
  UCHAR                        ErrStatusAddressSpaceID;
  UCHAR                        ErrStatusAddressBitWidth;
  UCHAR                        ErrStatusAddressBitOffset;
  UCHAR                        ErrStatusAddressAccessSize;
  WHEA_PHYSICAL_ADDRESS        ErrStatusAddress;
  WHEA_NOTIFICATION_DESCRIPTOR Notify;
} *PWHEA_GENERIC_ERROR_DESCRIPTOR, WHEA_GENERIC_ERROR_DESCRIPTOR;
```

## Members


`Type`

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_GENERIC.

`Reserved`

Reserved for system use.

`Enabled`

A Boolean value that indicates if the error source is enabled.

`ErrStatusBlockLength`

The size, in bytes, of the block of error status registers that contain the error data for the error source.

`RelatedErrorSourceId`

The identifier of the related error source. If the generic error source does not relate back to another error source, this member is not used.

`ErrStatusAddressSpaceID`

The address space of the address that is specified in the <b>ErrStatusAddress</b> member. Possible values are:





#### 0x00

System memory space



#### 0x01

System I/O space



#### 0x02

PCI configuration space



#### 0x03

Embedded controller address space



#### 0x04

System management bus (SMBus) address space



#### 0x05 - 0x7E

Reserved



#### 0x7F

Functional fixed hardware address space



#### 0x80 - 0xBF

Reserved



#### 0xC0 - 0xFF

OEM defined address space

`ErrStatusAddressBitWidth`

The size, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.

`ErrStatusAddressBitOffset`

The offset, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.

`ErrStatusAddressAccessSize`

The access size for reading the register at the address that is specified in the <b>ErrStatusAddress</b> member. Possible values are:





#### 0

Undefined



#### 1

Byte access



#### 2

Word access



#### 3

Double word access



#### 4

Quad word access

`ErrStatusAddress`

The 64-bit address of a register that contains the physical address of a block of memory that contains the error status data for the error source. This block of memory must reside in firmware reserved memory so that it is not reclaimed by the operating system's memory manager. The error status data contained in this block of memory is described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a> structure.

`Notify`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560574">WHEA_NOTIFICATION_DESCRIPTOR</a> structure that describes the notification mechanism that is used by the error source.

## Remarks
A WHEA_GENERIC_ERROR_DESCRIPTOR structure is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560574">WHEA_NOTIFICATION_DESCRIPTOR</a>