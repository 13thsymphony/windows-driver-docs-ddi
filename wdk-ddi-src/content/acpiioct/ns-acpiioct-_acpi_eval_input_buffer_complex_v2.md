---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2
title: "_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2"
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure.
old-location: acpi\acpi_eval_input_buffer_complex_v2.htm
old-project: acpi
ms.assetid: EAF78C14-7BE1-4441-B372-5AB0711E1F19
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, acpi.acpi_eval_input_buffer_complex_v2, acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2"
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
-	ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure
This topic describes the <b>ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2</b> structure.

## Syntax
```
typedef struct _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 {
  ULONG                   Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  } DUMMYUNIONNAME;
  ULONG                   Size;
  ULONG                   ArgumentCount;
  ACPI_METHOD_ARGUMENT_V2 Argument[ANYSIZE_ARRAY];
} ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2;
```

## Members


`Signature`

Defines the <b>ULONG</b> member <b>Signature</b>.

`DUMMYUNIONNAME`

Defines the method name member of <b>DUMMYUNIONNAME</b>.

`Size`

Defines the <b>ULONG</b> member <b>Size</b>.

`ArgumentCount`

Defines the <b>ULONG</b> member <b>ArgumentCount</b>.

`Argument`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 and later versions. Windows 10, version 1709 and later versions. |
| **Header** | acpiioct.h (include Acpiioct.h) |