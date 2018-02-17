---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX
title: "_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX"
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX structure.
old-location: acpi\acpi_eval_input_buffer_simple_integer_v2_ex.htm
old-project: acpi
ms.assetid: 26F68B49-8205-4132-93E7-BFE8FE695D9C
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: acpi.acpi_eval_input_buffer_simple_integer_v2_ex, acpiioct/PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX structure pointer [ACPI Devices], *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX structure [ACPI Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX
product: Windows
targetos: Windows
req.typenames: "*PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX"
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX structure
This topic describes the  <b>ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX</b> structure.

## Syntax
````
typedef struct _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX {
  ULONG                  Signature;
  _Null_terminated_ CHAR MethodName[256];
  ULONG64                IntegerArgument;
} ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX;
````

## Members


`IntegerArgument`

Defines the <b>ULONG64</b> member <b>IntegerArgument</b>.

`MethodName`



`Signature`

Defines the <b>ULONG</b> member <b>Signature</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 and later versions. Windows 10, version 1709 and later versions. |
| **Header** | acpiioct.h (include Acpiioct.h) |