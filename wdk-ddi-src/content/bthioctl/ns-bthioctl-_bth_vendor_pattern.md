---
UID: NS:bthioctl._BTH_VENDOR_PATTERN
title: "_BTH_VENDOR_PATTERN"
author: windows-driver-content
description: The BTH_VENDOR_PATTERN structure specifies a vendor pattern.
old-location: bltooth\bth_vendor_pattern.htm
old-project: bltooth
ms.assetid: 694020c6-dd0a-46c7-9122-cd86ce28d03a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTH_VENDOR_PATTERN, BTH_VENDOR_PATTERN, BTH_VENDOR_PATTERN structure [Bluetooth Devices], PBTH_VENDOR_PATTERN, PBTH_VENDOR_PATTERN structure pointer [Bluetooth Devices], _BTH_VENDOR_PATTERN, bltooth.bth_vendor_pattern, bth_ref_e5c1f867-d585-4c90-bfe1-7b3c4a6e1582.xml, bthioctl/BTH_VENDOR_PATTERN, bthioctl/PBTH_VENDOR_PATTERN"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Available in Windows Vista, and later versions of Windows.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthioctl.h
api_name:
-	BTH_VENDOR_PATTERN
product: Windows
targetos: Windows
req.typenames: BTH_VENDOR_PATTERN, *PBTH_VENDOR_PATTERN
---

# _BTH_VENDOR_PATTERN structure
The BTH_VENDOR_PATTERN structure specifies a vendor pattern.

## Syntax
```
typedef struct _BTH_VENDOR_PATTERN {
  UCHAR Offset;
  UCHAR Size;
  UCHAR Pattern[1];
} BTH_VENDOR_PATTERN, *PBTH_VENDOR_PATTERN;
```

## Members


`Offset`

The offset, in bytes, of the pattern from the beginning of the event data, excluding the event
     header.

`Size`

The size, in bytes, of the pattern.

`Pattern`

A buffer that contains pattern data.

## Remarks
The BTH_VENDOR_PATTERN structure specifies vendor patterns for the 
    <a href="https://msdn.microsoft.com/c37844d9-206a-4060-8b46-9afe691fe8f9">
    BTH_VENDOR_SPECIFIC_COMMAND</a> structure.

A list of patterns can immediately follow the vendor-specific command data that is specified in the 
    <b>Data</b> member of the BTH_VENDOR_SPECIFIC_COMMAND structure.

Patterns are required if a vendor-specific command does not follow the standard HCI flow control and a
    vendor-specific event is generated in response to the vendor-specific command.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Available in Windows Vista, and later versions of Windows. Versions:\_Available in Windows Vista, and later versions of Windows. |
| **Header** | bthioctl.h (include Bthioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536656">BTH_VENDOR_SPECIFIC_COMMAND</a>