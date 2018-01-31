---
UID : NS:ntddcdrm._CDROM_EXCLUSIVE_ACCESS
title : "_CDROM_EXCLUSIVE_ACCESS"
author : windows-driver-content
description : The CDROM_EXCLUSIVE_ACCESS structure is used with the IOCTL_CDROM_EXCLUSIVE_ACCESS request to query the access state of a CD-ROM device or to lock or unlock the device for exclusive access.
old-location : storage\cdrom_exclusive_access.htm
old-project : storage
ms.assetid : 95248a4a-1fc1-4985-baff-2fe77532d398
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : "*PCDROM_EXCLUSIVE_ACCESS, CDROM_EXCLUSIVE_ACCESS, PCDROM_EXCLUSIVE_ACCESS, structs-CD-ROM_f9104134-3d0a-44fd-9a2d-9dd4e8a3636d.xml, storage.cdrom_exclusive_access, CDROM_EXCLUSIVE_ACCESS structure [Storage Devices], ntddcdrm/PCDROM_EXCLUSIVE_ACCESS, PCDROM_EXCLUSIVE_ACCESS structure pointer [Storage Devices], ntddcdrm/CDROM_EXCLUSIVE_ACCESS, _CDROM_EXCLUSIVE_ACCESS"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddcdrm.h
req.include-header : Ntddcdrm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PCDROM_EXCLUSIVE_ACCESS, CDROM_EXCLUSIVE_ACCESS"
---

# _CDROM_EXCLUSIVE_ACCESS structure
The CDROM_EXCLUSIVE_ACCESS structure is used with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a> request to query the access state of a CD-ROM device or to lock or unlock the device for exclusive access.

## Syntax
````
typedef struct _CDROM_EXCLUSIVE_ACCESS {
  EXCLUSIVE_ACCESS_REQUEST_TYPE RequestType;
  ULONG                         Flags;
} CDROM_EXCLUSIVE_ACCESS, *PCDROM_EXCLUSIVE_ACCESS;
````

## Members


`Flags`

A flag that specifies the characteristics of the operation. The meaning of the flag depends on the type of operation that <b>RequestType</b> specifies. The following table describes the possible values for <b>RequestType</b> and <b>Flags</b>:
<table>
<tr>
<th>RequestType</th>
<th>Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>ExclusiveAccessQueryState</b>

</td>
<td>
Not applicable

</td>
<td>
Not applicable

</td>
</tr>
<tr>
<td rowspan="2">
<b>ExclusiveAccessLockDevice</b>

</td>
<td>
0

</td>
<td>
Requires that the caller dismount the file system

</td>
</tr>
<tr>
<td>
CDROM_LOCK_IGNORE_VOLUME

</td>
<td>
Ignores the file system mount and locks the device

</td>
</tr>
<tr>
<td>
<b>ExclusiveAccessUnlockDevice</b>

</td>
<td>
CDROM_NO_MEDIA_NOTIFICATIONS

</td>
<td>
Prevents the sending of a media removal notification and a media arrival notification on an exclusive access unlock

</td>
</tr>
</table>

`RequestType`

An <a href="..\ntddcdrm\ne-ntddcdrm-_exclusive_access_request_type.md">EXCLUSIVE_ACCESS_REQUEST_TYPE</a>-typed enumeration value that specifies the type of operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_EXCLUSIVE_ACCESS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>