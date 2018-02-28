---
UID: NS:ntddstor._STORAGE_MINIPORT_DESCRIPTOR
title: "_STORAGE_MINIPORT_DESCRIPTOR"
author: windows-driver-content
description: Reserved for system use.
old-location: storage\storage_miniport_descriptor.htm
old-project: storage
ms.assetid: 30497CA8-70B6-48F9-B5D5-45E606A3226E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSTORAGE_MINIPORT_DESCRIPTOR, PSTORAGE_MINIPORT_DESCRIPTOR, PSTORAGE_MINIPORT_DESCRIPTOR structure pointer [Storage Devices], STORAGE_MINIPORT_DESCRIPTOR, STORAGE_MINIPORT_DESCRIPTOR structure [Storage Devices], _STORAGE_MINIPORT_DESCRIPTOR, ntddstor/PSTORAGE_MINIPORT_DESCRIPTOR, ntddstor/STORAGE_MINIPORT_DESCRIPTOR, storage.storage_miniport_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
-	ntddstor.h
api_name:
-	STORAGE_MINIPORT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_MINIPORT_DESCRIPTOR, *PSTORAGE_MINIPORT_DESCRIPTOR
---

# _STORAGE_MINIPORT_DESCRIPTOR structure
Reserved for system use.

## Syntax
````
typedef struct _STORAGE_MINIPORT_DESCRIPTOR {
  ULONG                 Version;
  ULONG                 Size;
  STORAGE_PORT_CODE_SET Portdriver;
  BOOLEAN               LUNResetSupported;
  BOOLEAN               TargetResetSupported;
  USHORT                IoTimeoutValue;
  BOOLEAN               ExtraIoInfoSupported;
  UCHAR                 Reserved0[3];
  UCHAR                 Reserved1;
} STORAGE_MINIPORT_DESCRIPTOR, *PSTORAGE_MINIPORT_DESCRIPTOR;
````

## Members


`ExtraIoInfoSupported`

<b>Introduced in Windows 8.1:  </b>Indicates if extra I/O info is supported.

`IoTimeoutValue`

<b>Introduced in Windows 8:  </b>Indicates the timeout value for the device, in milliseconds (ms).

`LUNResetSupported`

Indicates whether a LUN reset is supported.

`Portdriver`

Type of port driver as enumerated by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/mt668773">STORAGE_PORT_CODE_SET</a> enumeration.

`Reserved0`

<b>Introduced in Windows 8.1:  </b>Reserved for future use.

`Reserved1`

<b>Introduced in Windows 8.1:  </b>Reserved for future use.

`Size`

Specifies the total size of the data returned, in bytes. This may include data that follows this 
      structure.

`TargetResetSupported`

Indicates whether a target reset is supported.

`Version`

Contains the size of this structure, in bytes. The value of this member will change as members are added to 
      the structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows Vista Windows Vista |
| **Header** | ntddstor.h (include Ntddstor.h) |