---
UID: NS.ACPIIOCT._ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2
title: _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2 structure.
old-location: acpi\acpi_eval_input_buffer_simple_string_v2.htm
old-project: acpi
ms.assetid: AB120BA9-0E52-489E-AB51-866D8A020DAC
ms.author: windowsdriverdev
ms.date: 12/2/2017
ms.keywords: _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2
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
req.alt-api: ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2
req.alt-loc: Acpiioct.h
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
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2 structure



## -description
This topic describes the  <b>ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2</b> structure.


## -syntax

````
typedef struct _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2 {
  ULONG                                                        Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  } DUMMYUNIONNAME;
  ULONG                                                        StringLength;
  _Field_size_bytes_(StringLength)
    _Null_terminated_ UCHAR String[ANYSIZE_ARRAY];
} ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2;
````


## -struct-fields

### -field Signature

Defines the <b>ULONG</b> member <b>Signature</b>.

### -field DUMMYUNIONNAME

Defines the method name member of <b>DUMMYUNIONNAME</b>.

### -field StringLength

Defines the <b>ULONG</b> member <b>StringLength</b>.

### -field String[ANYSIZE_ARRAY]

Defines the <b>UCHAR</b> member <b>String[ANYSIZE_ARRAY]</b>.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Windows 10, version 1709 and later versions.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
</dl>
</td>
</tr>
</table>