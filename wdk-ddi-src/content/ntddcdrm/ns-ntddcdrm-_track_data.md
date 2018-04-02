---
UID: NS:ntddcdrm._TRACK_DATA
title: "_TRACK_DATA"
author: windows-driver-content
description: Track descriptor is used in conjunction with CDROM_TOC and CDROM_TOC_SESSION_DATA.
old-location: storage\track_data.htm
old-project: storage
ms.assetid: f412ff4e-6c65-40f8-9747-dc5059e588f6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PTRACK_DATA, PTRACK_DATA, PTRACK_DATA structure pointer [Storage Devices], TRACK_DATA, TRACK_DATA structure [Storage Devices], _TRACK_DATA, ntddcdrm/PTRACK_DATA, ntddcdrm/TRACK_DATA, storage.track_data, structs-CD-ROM_37ea4578-82b7-4b8e-be1b-28c27de349d9.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	TRACK_DATA
product:
- Windows
targetos: Windows
req.typenames: TRACK_DATA, *PTRACK_DATA
---

# _TRACK_DATA structure
Track descriptor is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff551373">CDROM_TOC</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551389">CDROM_TOC_SESSION_DATA</a>.

## Syntax
```
typedef struct _TRACK_DATA {
  UCHAR      Reserved;
  UCHAR  : 4 Control;
  UCHAR  : 4 Adr;
  UCHAR      TrackNumber;
  UCHAR      Reserved1;
  UCHAR      Address[4];
} *PTRACK_DATA, TRACK_DATA;
```

## Members


`Reserved`

Reserved.

`Control`

Indicates the attributes of the track. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS).

`Adr`

Indicates the type of information encoded in the Q subchannel of the track where this table of contents entry was found. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS).

`TrackNumber`

Indicates the number of the track.

`Reserved1`

Reserved.

`Address`

Indicates the starting address of the track.

## Remarks
This structure contains table of contents information for a track.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551373">CDROM_TOC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551389">CDROM_TOC_SESSION_DATA</a>