---
UID: NE:ntddcdrm._EXCLUSIVE_ACCESS_REQUEST_TYPE
title: "_EXCLUSIVE_ACCESS_REQUEST_TYPE"
author: windows-driver-content
description: The EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration is used to report the exclusive access state of a CD-ROM device.
old-location: storage\exclusive_access_request_type.htm
old-project: storage
ms.assetid: 314dfdeb-1821-444a-84c6-2ee7fa536122
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PEXCLUSIVE_ACCESS_REQUEST_TYPE, EXCLUSIVE_ACCESS_REQUEST_TYPE, EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration [Storage Devices], ExclusiveAccessLockDevice, ExclusiveAccessQueryState, ExclusiveAccessUnlockDevice, PEXCLUSIVE_ACCESS_REQUEST_TYPE, PEXCLUSIVE_ACCESS_REQUEST_TYPE enumeration pointer [Storage Devices], _EXCLUSIVE_ACCESS_REQUEST_TYPE, ntddcdrm/EXCLUSIVE_ACCESS_REQUEST_TYPE, ntddcdrm/ExclusiveAccessLockDevice, ntddcdrm/ExclusiveAccessQueryState, ntddcdrm/ExclusiveAccessUnlockDevice, ntddcdrm/PEXCLUSIVE_ACCESS_REQUEST_TYPE, storage.exclusive_access_request_type, structs-CD-ROM_0b0d7aae-3085-422c-84c4-555d935ca176.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	EXCLUSIVE_ACCESS_REQUEST_TYPE
product:
- Windows
targetos: Windows
req.typenames: EXCLUSIVE_ACCESS_REQUEST_TYPE, *PEXCLUSIVE_ACCESS_REQUEST_TYPE
---

# _EXCLUSIVE_ACCESS_REQUEST_TYPE Enumeration
The EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration is used to report the exclusive access state of a CD-ROM device.

## Syntax
```
typedef enum _EXCLUSIVE_ACCESS_REQUEST_TYPE {
  ExclusiveAccessQueryState    ,
  ExclusiveAccessLockDevice    ,
  ExclusiveAccessUnlockDevice
} *PEXCLUSIVE_ACCESS_REQUEST_TYPE, EXCLUSIVE_ACCESS_REQUEST_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>ExclusiveAccessQueryState</td>
                    <td>A query for the access state of a CD-ROM device.</td>
                </tr>
            
                <tr>
                    <td>ExclusiveAccessLockDevice</td>
                    <td>A request for the CD-ROM class driver to lock a CD-ROM device for exclusive access by the caller.</td>
                </tr>
            
                <tr>
                    <td>ExclusiveAccessUnlockDevice</td>
                    <td>A request for the CD-ROM class driver to unlock a CD-ROM device that was previously locked for exclusive access.</td>
                </tr>
</table>

## Remarks

The EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559327">IOCTL_CDROM_EXCLUSIVE_ACCESS</a> request to query the access state of a CD-ROM device or to lock or unlock the device for exclusive access.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559327">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>