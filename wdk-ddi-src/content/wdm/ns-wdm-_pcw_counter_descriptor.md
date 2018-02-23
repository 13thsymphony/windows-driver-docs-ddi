---
UID: NS:wdm._PCW_COUNTER_DESCRIPTOR
title: "_PCW_COUNTER_DESCRIPTOR"
author: windows-driver-content
description: The PCW_COUNTER_DESCRIPTOR structure supplies details about the notification to send.
old-location: devtest\pcw_counter_descriptor.htm
old-project: devtest
ms.assetid: 0b099aec-f254-4cfb-87cb-2f8965d5faae
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_PCW_COUNTER_DESCRIPTOR, devtest.pcw_counter_descriptor, wdm/PCW_COUNTER_DESCRIPTOR, *PPCW_COUNTER_DESCRIPTOR, PPCW_COUNTER_DESCRIPTOR, PPCW_COUNTER_DESCRIPTOR structure pointer [Driver Development Tools], wdm/PPCW_COUNTER_DESCRIPTOR, PCW_COUNTER_DESCRIPTOR, km_pcw_8507bc5e-60f4-4b71-bb2f-d62360076e2c.xml, PCW_COUNTER_DESCRIPTOR structure [Driver Development Tools]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	PCW_COUNTER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PPCW_COUNTER_DESCRIPTOR, PCW_COUNTER_DESCRIPTOR"
req.product: Windows 10 or later.
---

# _PCW_COUNTER_DESCRIPTOR structure
The PCW_COUNTER_DESCRIPTOR structure supplies details about the notification to send.

## Syntax
````
typedef struct _PCW_COUNTER_DESCRIPTOR {
  USHORT Id;
  USHORT StructIndex;
  USHORT Offset;
  USHORT Size;
} PCW_COUNTER_DESCRIPTOR, *PPCW_COUNTER_DESCRIPTOR;
````

## Members


`Id`

A numeric value that specifies the <b>Id</b> (identifier) associated with the instance of the counter set.

`Offset`

A numeric value that indicates the end of the instance list for the counter set. The value is used to ensure that a new instance will always be added to the end of the list.

`Size`

A numeric value that specifies the size, in bytes, associated with the instance of the counter set.

`StructIndex`

A numeric value that specifies the index into the array of structures that describe the counter set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |