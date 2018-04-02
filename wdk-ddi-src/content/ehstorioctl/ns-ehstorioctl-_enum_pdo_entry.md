---
UID: NS:ehstorioctl._ENUM_PDO_ENTRY
title: "_ENUM_PDO_ENTRY"
author: windows-driver-content
description: This structure describes a single entry in a result set of Physical Device Objects (PDOs) that are enumerated with IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS.
old-location: storage\enum_pdo_entry.htm
old-project: storage
ms.assetid: c3f5cc8e-a600-4ca1-8745-d74943feb2c7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PENUM_PDO_ENTRY, ENUM_PDO_ENTRY, ENUM_PDO_ENTRY structure [Storage Devices], PENUM_PDO_ENTRY, PENUM_PDO_ENTRY structure pointer [Storage Devices], _ENUM_PDO_ENTRY, ehstorioctl/ENUM_PDO_ENTRY, ehstorioctl/PENUM_PDO_ENTRY, storage.enum_pdo_entry, structs-silo_8303b6a6-8f4f-4f0c-91ce-9d70ea72f4f2.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
-	EhStorIoctl.h
api_name:
-	ENUM_PDO_ENTRY
product:
- Windows
targetos: Windows
req.typenames: ENUM_PDO_ENTRY, *PENUM_PDO_ENTRY
---

# _ENUM_PDO_ENTRY structure
This structure describes a single entry in a result set of Physical Device Objects (PDOs) that are enumerated with <a href="https://msdn.microsoft.com/library/windows/hardware/hh451409">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>.

## Syntax
```
typedef struct _ENUM_PDO_ENTRY {
  UCHAR type;
  UCHAR state;
  UCHAR capabilities;
  ULONG ulSTID;
  UCHAR bSpecificationMajor;
  UCHAR bSpecificationMinor;
  UCHAR bImplementationMajor;
  UCHAR bImplementationMinor;
  WCHAR *wszDeviceInstancePath[(2  MAX_PATH)+ 1];
} ENUM_PDO_ENTRY, *PENUM_PDO_ENTRY;
```

## Members


`type`

This member indicates the type of the PDO that is being identified, as defined by PDO_TYPE.

`state`

This member contains information about the current PnP state of the PDO, as defined by PDO_STATE.

`capabilities`

This member contains a bitmask with bits indicating information about the silo represented by the PDO in question, as defined by PDO_CAPS.

`ulSTID`

This member contains the silo type identifier, as defined and assigned by the IEEE 1667 working group.

`bSpecificationMajor`



`bSpecificationMinor`



`bImplementationMajor`



`bImplementationMinor`



`wszDeviceInstancePath`

The string contained in this member is the device instance path in a form suitable for use with the Win32 API CreateFile routine.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451409">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>