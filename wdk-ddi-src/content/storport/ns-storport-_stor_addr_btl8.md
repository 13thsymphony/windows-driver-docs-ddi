---
UID: NS:storport._STOR_ADDR_BTL8
title: "_STOR_ADDR_BTL8"
author: windows-driver-content
description: The STOR_ADDR_BTL8 address structure contains the addressing information for an 8-bit Bus-Target-LUN (BTL8) address.
old-location: storage\stor_addr_btl8.htm
old-project: storage
ms.assetid: 53C8A5D4-4D8B-4D3E-A350-B3BBAC7F8C71
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTOR_ADDR_BTL8, PSTOR_ADDR_BTL8, PSTOR_ADDR_BTL8 structure pointer [Storage Devices], STOR_ADDR_BTL8, STOR_ADDR_BTL8 structure [Storage Devices], _STOR_ADDR_BTL8, storage.stor_addr_btl8, storport/PSTOR_ADDR_BTL8, storport/STOR_ADDR_BTL8"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Scsi.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	Storport.h
api_name:
-	STOR_ADDR_BTL8
product: Windows
targetos: Windows
req.typenames: STOR_ADDR_BTL8, *PSTOR_ADDR_BTL8
req.product: Windows 10 or later.
---

# _STOR_ADDR_BTL8 structure
The <b>STOR_ADDR_BTL8</b> address structure contains the addressing information for an 8-bit Bus-Target-LUN (BTL8) address.

## Syntax
```
typedef struct _STOR_ADDR_BTL8 {
  USHORT Type;
  USHORT Port;
  ULONG  AddressLength;
  UCHAR  Path;
  UCHAR  Target;
  UCHAR  Lun;
  UCHAR  Reserved;
} STOR_ADDR_BTL8, *PSTOR_ADDR_BTL8;
```

## Members


`Type`

The address type. This member is set to <b>STOR_ADDRESS_TYPE_BTL8</b>.

`Port`

The host bus adapter (HBA) port number.

`AddressLength`

The byte length of the address. This value is set to <b>STOR_ADDR_BTL8_ADDRESS_LENGTH</b>.

`Path`

The bus number for the target device.

`Target`

The target device number.

`Lun`

The logical unit on the target device.

`Reserved`

Reserved, set to 0.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | storport.h (include Storport.h, Scsi.h, Minitape.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451518">STOR_ADDRESS</a>