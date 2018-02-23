---
UID: NS:wdm._PCW_DATA
title: "_PCW_DATA"
author: windows-driver-content
description: The PCW_DATA structure describes the array of data blocks that are associated with an instance.
old-location: devtest\pcw_data.htm
old-project: devtest
ms.assetid: c2da567a-cea6-497a-b50f-848ecac20b30
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PPCW_DATA structure pointer [Driver Development Tools], km_pcw_69759b50-4312-4997-ba43-4ce30941d502.xml, wdm/PPCW_DATA, PPCW_DATA, *PPCW_DATA, _PCW_DATA, PCW_DATA, PCW_DATA structure [Driver Development Tools], devtest.pcw_data, wdm/PCW_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 or later versions of Windows.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCW_DATA
product: Windows
targetos: Windows
req.typenames: "*PPCW_DATA, PCW_DATA"
req.product: Windows 10 or later.
---

# _PCW_DATA structure
The PCW_DATA structure describes the array of data blocks that are associated with an instance.

## Syntax
````
typedef struct _PCW_DATA {
  const VOID *Data;
  ULONG      Size;
} PCW_DATA, *PPCW_DATA;
````

## Members


`Data`

A <b>const</b> pointer to a buffer of <b>Size</b> bytes.

`Size`

A numeric value that specifies the size, in bytes, associated with the instance of the counter set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 or later versions of Windows. Available in Windows 7 or later versions of Windows. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |