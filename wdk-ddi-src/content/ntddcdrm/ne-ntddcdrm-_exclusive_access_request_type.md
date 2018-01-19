---
UID : NE:ntddcdrm._EXCLUSIVE_ACCESS_REQUEST_TYPE
title : _EXCLUSIVE_ACCESS_REQUEST_TYPE
author : windows-driver-content
description : The EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration is used to report the exclusive access state of a CD-ROM device.
old-location : storage\exclusive_access_request_type.htm
old-project : storage
ms.assetid : 314dfdeb-1821-444a-84c6-2ee7fa536122
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _EXCLUSIVE_ACCESS_REQUEST_TYPE, *PEXCLUSIVE_ACCESS_REQUEST_TYPE, EXCLUSIVE_ACCESS_REQUEST_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddcdrm.h
req.include-header : Ntddcdrm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : EXCLUSIVE_ACCESS_REQUEST_TYPE
req.alt-loc : ntddcdrm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PEXCLUSIVE_ACCESS_REQUEST_TYPE, EXCLUSIVE_ACCESS_REQUEST_TYPE"
---

# _EXCLUSIVE_ACCESS_REQUEST_TYPE Enumeration
The EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration is used to report the exclusive access state of a CD-ROM device.

## Syntax
````
typedef enum _EXCLUSIVE_ACCESS_REQUEST_TYPE { 
  ExclusiveAccessQueryState    = 0,
  ExclusiveAccessLockDevice    = 1,
  ExclusiveAccessUnlockDevice  = 2
} EXCLUSIVE_ACCESS_REQUEST_TYPE, *PEXCLUSIVE_ACCESS_REQUEST_TYPE;
````

## Constants

<table>

<tr>
<td>ExclusiveAccessLockDevice</td>
<td>A request for the CD-ROM class driver to lock a CD-ROM device for exclusive access by the caller.</td>
</tr>

<tr>
<td>ExclusiveAccessQueryState</td>
<td>A query for the access state of a CD-ROM device.</td>
</tr>

<tr>
<td>ExclusiveAccessUnlockDevice</td>
<td>A request for the CD-ROM class driver to unlock a CD-ROM device that was previously locked for exclusive access.</td>
</tr>
</table>

## Remarks

The EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration is used with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a> request to query the access state of a CD-ROM device or to lock or unlock the device for exclusive access.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>