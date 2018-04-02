---
UID: NE:ntddcdrm._TRACK_MODE_TYPE
title: "_TRACK_MODE_TYPE"
author: windows-driver-content
description: The TRACK_MODE_TYPE enumeration type is used in conjunction with the IOCTL_CDROM_RAW_READ request and the RAW_READ_INFO structure to read data from a CD-ROM in raw mode.
old-location: storage\track_mode_type.htm
old-project: storage
ms.assetid: ea7d7b5a-625f-41f7-b3fd-96a6bf338db9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PTRACK_MODE_TYPE, CDDA, PTRACK_MODE_TYPE, PTRACK_MODE_TYPE enumeration pointer [Storage Devices], RawWithC2, RawWithC2AndSubCode, RawWithSubCode, TRACK_MODE_TYPE, TRACK_MODE_TYPE enumeration [Storage Devices], XAForm2, YellowMode2, _TRACK_MODE_TYPE, ntddcdrm/CDDA, ntddcdrm/PTRACK_MODE_TYPE, ntddcdrm/RawWithC2, ntddcdrm/RawWithC2AndSubCode, ntddcdrm/RawWithSubCode, ntddcdrm/TRACK_MODE_TYPE, ntddcdrm/XAForm2, ntddcdrm/YellowMode2, storage.track_mode_type, structs-CD-ROM_41364f33-e1bf-48ac-abb6-4cacf5283f9f.xml"
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
-	TRACK_MODE_TYPE
product: Windows
targetos: Windows
req.typenames: TRACK_MODE_TYPE, *PTRACK_MODE_TYPE
---

# _TRACK_MODE_TYPE Enumeration
The TRACK_MODE_TYPE enumeration type is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559361">IOCTL_CDROM_RAW_READ</a> request and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563958">RAW_READ_INFO</a> structure to read data from a CD-ROM in raw mode.

## Syntax
```
typedef enum _TRACK_MODE_TYPE {
  YellowMode2          ,
  XAForm2              ,
  CDDA                 ,
  RawWithC2AndSubCode  ,
  RawWithC2            ,
  RawWithSubCode
} TRACK_MODE_TYPE, *PTRACK_MODE_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>YellowMode2</td>
                    <td>Indicates that CD-ROM mode should be used. This mode is used with read-only 120 mm Optical Data Discs (CD-ROM). For more information, see the ISO/IEC 10149 specification.</td>
                </tr>
            
                <tr>
                    <td>XAForm2</td>
                    <td>Indicates that compact disc read-only memory extended architecture mode should be used. For more information see the specification for CD-ROM XA published by NV Philips and Sony Corporation.</td>
                </tr>
            
                <tr>
                    <td>CDDA</td>
                    <td>Indicates that digital audio information mode should be used. For more information, see the IEC 908:1987 specification.</td>
                </tr>
            
                <tr>
                    <td>RawWithC2AndSubCode</td>
                    <td>CD_RAW_SECTOR_WITH_C2_AND_SUBCODE_SIZE per sector</td>
                </tr>
            
                <tr>
                    <td>RawWithC2</td>
                    <td>CD_RAW_SECTOR_WITH_C2_SIZE per sector</td>
                </tr>
            
                <tr>
                    <td>RawWithSubCode</td>
                    <td>CD_RAW_SECTOR_WITH_SUBCODE_SIZE per sector</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559361">IOCTL_CDROM_RAW_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563958">RAW_READ_INFO</a>