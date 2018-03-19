---
UID: NE:ntddcdrm._CDROM_SPEED_REQUEST
title: "_CDROM_SPEED_REQUEST"
author: windows-driver-content
description: The CDROM_SPEED_REQUEST enumeration indicates which command that the CD-ROM class driver will use to set the spindle speed of a CD-ROM drive.
old-location: storage\cdrom_speed_request.htm
old-project: storage
ms.assetid: 147d2c1c-c12d-4c39-bec5-579ece083ee7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_SPEED_REQUEST, CDROM_SPEED_REQUEST, CDROM_SPEED_REQUEST enumeration [Storage Devices], CdromSetSpeed, CdromSetStreaming, PCDROM_SPEED_REQUEST, PCDROM_SPEED_REQUEST enumeration pointer [Storage Devices], _CDROM_SPEED_REQUEST, ntddcdrm/CDROM_SPEED_REQUEST, ntddcdrm/CdromSetSpeed, ntddcdrm/CdromSetStreaming, ntddcdrm/PCDROM_SPEED_REQUEST, storage.cdrom_speed_request, structs-CD-ROM_6feeaa4e-8500-4ca8-9d0f-3e29a858eb94.xml"
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
-	CDROM_SPEED_REQUEST
product: Windows
targetos: Windows
req.typenames: CDROM_SPEED_REQUEST, *PCDROM_SPEED_REQUEST
---

# _CDROM_SPEED_REQUEST Enumeration
The CDROM_SPEED_REQUEST enumeration indicates which command that the CD-ROM class driver will use to set the spindle speed of a CD-ROM drive.

## Syntax
````
typedef enum _CDROM_SPEED_REQUEST { 
  CdromSetSpeed      = 0,
  CdromSetStreaming  = 1
} CDROM_SPEED_REQUEST, *PCDROM_SPEED_REQUEST;
````

## Constants

<table>
            
                <tr>
                    <td>CdromSetSpeed</td>
                    <td>The CD-ROM class driver will use the SET CD SPEED command to set the spindle speed.</td>
                </tr>
            
                <tr>
                    <td>CdromSetStreaming</td>
                    <td>The CD-ROM class driver will use the SET STREAMING command to set the spindle speed.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_set_speed.md">IOCTL_CDROM_SET_SPEED</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_set_streaming.md">CDROM_SET_STREAMING</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_set_speed.md">CDROM_SET_SPEED</a>