---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2
title: "_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2"
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2 structure.
old-location: acpi\acpi_eval_input_buffer_simple_integer_v2.htm
old-project: acpi
ms.assetid: 47771F52-5927-40DC-907E-0FC9C3FD451A
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2 structure [ACPI Devices], acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2, _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2, PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2, PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2 structure pointer [ACPI Devices], acpi.acpi_eval_input_buffer_simple_integer_v2, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2, acpiioct/PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2
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
-	ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2 structure
This topic describes the  <b>ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2</b> structure.

## Syntax
````
typedef struct _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2 {
  ULONG Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  } DUMMYUNIONNAME;
  ULONG IntegerArgument;
} ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2;
````

## Members


`DUMMYUNIONNAME`

Defines the method name member of <b>DUMMYUNIONNAME</b>.

`IntegerArgument`

Defines the <b>ULONG</b> member <b>IntegerArgument</b>.

`Signature`

Defines the <b>ULONG</b> member <b>Signature</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 and later versions. Windows 10, version 1709 and later versions. |
| **Header** | acpiioct.h (include Acpiioct.h) |