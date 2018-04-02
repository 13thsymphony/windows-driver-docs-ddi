---
UID: NS:ksmedia.tagKS_AMVPDIMINFO
title: tagKS_AMVPDIMINFO
author: windows-driver-content
description: The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.
old-location: stream\ks_amvpdiminfo.htm
old-project: stream
ms.assetid: 5b8126ee-ba47-4eaf-887a-764e17a20e03
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_AMVPDIMINFO, KS_AMVPDIMINFO, KS_AMVPDIMINFO structure [Streaming Media Devices], PKS_AMVPDIMINFO, PKS_AMVPDIMINFO structure pointer [Streaming Media Devices], dvdref_4c6b6231-a3ef-49a5-8b27-c7ba0062c53a.xml, ksmedia/KS_AMVPDIMINFO, ksmedia/PKS_AMVPDIMINFO, stream.ks_amvpdiminfo, tagKS_AMVPDIMINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
api_name:
-	KS_AMVPDIMINFO
product: Windows
targetos: Windows
req.typenames: KS_AMVPDIMINFO, *PKS_AMVPDIMINFO
---

# tagKS_AMVPDIMINFO structure
The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.

## Syntax
```
typedef struct tagKS_AMVPDIMINFO {
  DWORD dwFieldWidth;
  DWORD dwFieldHeight;
  DWORD dwVBIWidth;
  DWORD dwVBIHeight;
  RECT  rcValidRegion;
} KS_AMVPDIMINFO, *PKS_AMVPDIMINFO;
```

## Members


`dwFieldWidth`

Specifies the field width.

`dwFieldHeight`

Specifies the field height.

`dwVBIWidth`

Specifies the VBI data width.

`dwVBIHeight`

Specifies the VBI data height.

`rcValidRegion`

Describes a valid rectangle for data cropping.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567261">KS_AMVPDATAINFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567261">KS_AMVPDATAINFO</a>