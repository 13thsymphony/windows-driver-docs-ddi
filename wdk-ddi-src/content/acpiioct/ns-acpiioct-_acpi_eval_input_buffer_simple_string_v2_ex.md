---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX
title: "_ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX"
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure.
old-location: acpi\acpi_eval_input_buffer_simple_string_v2_ex.htm
old-project: acpi
ms.assetid: 627DA82C-CD51-4FA0-80C2-03F7FA26C0CF
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, acpi.acpi_eval_input_buffer_simple_string_v2_ex, acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, acpiioct/PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 and later versions.
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
-	Acpiioct.h
api_name:
-	ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure
This topic describes the  <b>ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX</b> structure.

## Syntax
````
typedef struct _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX {
  ULONG                                                  Signature;
  CHAR                                                   MethodName[256];
  ULONG                                                  StringLength;
  _Field_size_(StringLength)
    _Null_terminated_ UCHAR String[ANYSIZE_ARRAY];
} ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX;
````

## Members


`Signature`

Defines the <b>ULONG</b> member <b>Signature</b>.

`MethodName`



`StringLength`

Defines the <b>ULONG</b> member <b>StringLength</b>.

`String`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 and later versions. Windows 10, version 1709 and later versions. |
| **Header** | acpiioct.h (include Acpiioct.h) |