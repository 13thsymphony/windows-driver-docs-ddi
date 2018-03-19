---
UID: NF:ntddk.WheaIsValidErrorRecordSignature
title: WheaIsValidErrorRecordSignature function
author: windows-driver-content
description: The WheaIsValidErrorRecordSignature function verifies whether a WHEA error record is valid.
old-location: whea\wheaisvaliderrorrecordsignature.htm
old-project: whea
ms.assetid: 35149395-4238-41fd-ae96-6491534e3cc1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WheaIsValidErrorRecordSignature, WheaIsValidErrorRecordSignature function [WHEA Drivers and Applications], ntddk/WheaIsValidErrorRecordSignature, whea.wheaisvaliderrorrecordsignature, whearef2_6ba74e00-cc1f-49e9-b6ee-b300571eb412.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WheaIsValidErrorRecordSignature
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# WheaIsValidErrorRecordSignature function
The <b>WheaIsValidErrorRecordSignature </b>function verifies whether a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> is valid.

## Syntax

````
BOOLEAN WheaIsValidErrorRecordSignature(
  _In_ PWHEA_ERROR_RECORD Record
);
````

## Parameters

`Record`

A pointer to a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> that is formatted as a <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> structure.


## Return Value

<b>WheaIsValidErrorRecordSignature </b>returns a Boolean value that indicates whether the WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> is valid. If it is valid, the function returns <b>TRUE</b>.

## Remarks

The <b>WheaIsValidErrorRecordSignature </b>function verifies that the specified <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> structure contains valid values.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows 7 and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | ntddk.h (include Ntddk.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a>



<a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>



<a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">Error record</a>