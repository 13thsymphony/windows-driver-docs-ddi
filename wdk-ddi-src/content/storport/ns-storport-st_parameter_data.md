---
UID: NS:storport.ST_PARAMETER_DATA
title: ST_PARAMETER_DATA
author: windows-driver-content
description: The ST_PARAMETER_DATA structure contains the parameter list for the set timestamp command.
old-location: storage\st_parameter_data.htm
old-project: storage
ms.assetid: C50F45EC-433C-421D-BD02-4C86CB44D5A4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PST_PARAMETER_DATA, PST_PARAMETER_DATA, PST_PARAMETER_DATA structure pointer [Storage Devices], ST_PARAMETER_DATA, ST_PARAMETER_DATA structure [Storage Devices], scsi/PST_PARAMETER_DATA, scsi/ST_PARAMETER_DATA, storage.st_parameter_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
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
-	scsi.h
api_name:
-	ST_PARAMETER_DATA
product: Windows
targetos: Windows
req.typenames: ST_PARAMETER_DATA, *PST_PARAMETER_DATA
req.product: Windows 10 or later.
---

# ST_PARAMETER_DATA structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>ST_PARAMETER_DATA</b> structure contains the parameter list for the set timestamp command.

## Syntax
```
typedef struct ST_PARAMETER_DATA {
  UCHAR Reserved1[4];
  UCHAR Timestamp[6];
  UCHAR Reserved2[2];
} *PST_PARAMETER_DATA, ST_PARAMETER_DATA;
```

## Members


`Reserved1`

Reserved for future use.

`Timestamp`

Specifies the value to which a device clock shall be initialized. The timestamp
should be the number of milliseconds that have elapsed since midnight, 1 January 1970 UT.

`Reserved2`

Reserved for future use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10, version 1709 and later versions of Windows. Available in Windows 10, version 1709 and later versions of Windows. |
| **Header** | storport.h (include Minitape.h, Storport.h) |

## See Also

<a href="https://msdn.microsoft.com/EB23D502-87E4-48B1-B1DC-0B215AB361C8">RT_PARAMETER_DATA</a>