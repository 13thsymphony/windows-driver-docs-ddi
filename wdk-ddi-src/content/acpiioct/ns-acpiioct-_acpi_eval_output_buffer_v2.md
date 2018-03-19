---
UID: NS:acpiioct._ACPI_EVAL_OUTPUT_BUFFER_V2
title: "_ACPI_EVAL_OUTPUT_BUFFER_V2"
author: windows-driver-content
description: This topic describes the ACPI_EVAL_OUTPUT_BUFFER_V2 structure.
old-location: acpi\acpi_eval_output_buffer_v2.htm
old-project: acpi
ms.assetid: 355A600E-F207-4A3F-80AE-EA2DAE810DA3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_EVAL_OUTPUT_BUFFER_V2, ACPI_EVAL_OUTPUT_BUFFER_V2, ACPI_EVAL_OUTPUT_BUFFER_V2 structure [ACPI Devices], _ACPI_EVAL_OUTPUT_BUFFER_V2, acpi.acpi_eval_output_buffer_v2, acpiioct/ACPI_EVAL_OUTPUT_BUFFER_V2"
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
-	ACPI_EVAL_OUTPUT_BUFFER_V2
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_OUTPUT_BUFFER_V2
---

# _ACPI_EVAL_OUTPUT_BUFFER_V2 structure
This topic describes the  <b>ACPI_EVAL_OUTPUT_BUFFER_V2</b> structure.

## Syntax
````
typedef struct _ACPI_EVAL_OUTPUT_BUFFER_V2 {
  ULONG                                                                                                           Signature;
  ULONG                                                                                                           Length;
  ULONG                                                                                                           Count;
  _Field_size_bytes_(Length - FIELD_OFFSET(struct _ACPI_EVAL_OUTPUT_BUFFER_V2, Argument)) ACPI_METHOD_ARGUMENT_V2 Argument[ANYSIZE_ARRAY];
} ACPI_EVAL_OUTPUT_BUFFER_V2;
````

## Members


`Signature`

Defines the <b>ULONG</b> member <b>Signature</b>.

`Length`

Defines the <b>ULONG</b> member <b>Length</b>.

`Count`

Defines the <b>ULONG</b> member <b>Count</b>.

`Argument`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 and later versions. Windows 10, version 1709 and later versions. |
| **Header** | acpiioct.h (include Acpiioct.h) |