---
UID : NS:dbgeng._DEBUG_VALUE
title : "_DEBUG_VALUE"
author : windows-driver-content
description : The DEBUG_VALUE structure holds register and expression values.
old-location : debugger\debug_value.htm
old-project : debugger
ms.assetid : 568469ad-79c4-4437-aefe-a29e77e5143a
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : "_DEBUG_VALUE, debugger.debug_value, dbgeng/DEBUG_VALUE, DEBUG_VALUE, PDEBUG_VALUE, DEBUG_VALUE structure [Windows Debugging], *PDEBUG_VALUE, dbgeng/PDEBUG_VALUE, PDEBUG_VALUE structure pointer [Windows Debugging], Structures_2486f31c-2a25-41eb-ac3f-9cc1d62dd2e0.xml"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dbgeng.h
req.include-header : DbgEng.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DEBUG_VALUE, *PDEBUG_VALUE
---

# _DEBUG_VALUE structure
The DEBUG_VALUE structure holds register and expression values.

## Syntax
````
typedef struct _DEBUG_VALUE {
  union {
    UCHAR   I8;
    USHORT  I16;
    ULONG   I32;
    struct {
      ULONG64 I64;
      BOOL    Nat;
    };
    float   F32;
    double  F64;
    UCHAR   F80Bytes[10];
    UCHAR   F82Bytes[11];
    UCHAR   F128Bytes[16];
    UCHAR   VI8[16];
    USHORT  VI16[8];
    ULONG   VI32[4];
    ULONG64 VI64[2];
    float   VF32[4];
    double  VF64[2];
    struct {
      ULONG LowPart;
      ULONG HighPart;
    } I64Parts32;
    struct {
      ULONG64 LowPart;
      LONG64  HighPart;
    } F128Parts64;
    UCHAR   RawBytes[24];
  };
  ULONG TailOfRawBytes;
  ULONG Type;
}  DEBUG_VALUE, *PDEBUG_VALUE;
````

## Members


`TailOfRawBytes`

See Remarks.

`Type`

See Remarks.

## Remarks
The <b>Type</b> field specifies the value type that is being held by the structure. This also specifies which field in the structure is valid. The possible values of the <b>Type</b> field, and the corresponding field specified as valid in the structure, include the following.
<table>
<tr>
<th>Type Name</th>
<th>Type</th>
<th>Valid DEBUG_VALUE Field</th>
</tr>
<tr>
<td>DEBUG_VALUE_INT8</td>
<td>8-bit signed integer</td>
<td><b>I8</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_INT16</td>
<td>16-bit signed integer</td>
<td><b>I16</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_INT32</td>
<td>32-bit signed integer</td>
<td><b>I32</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_INT64</td>
<td>64-bit signed integer</td>
<td><b>I64</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT32</td>
<td>32-bit floating point number</td>
<td><b>F32</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT64</td>
<td>64-bit floating point number</td>
<td><b>F64</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT80</td>
<td>80-bit floating point number</td>
<td><b>F80Bytes</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT128</td>
<td>128-bit floating point number</td>
<td><b>F128Bytes</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_VECTOR64</td>
<td>64-bit vector</td>
<td><b>VI8[8]</b>, <b>VI16[4]</b>, <b>VI32[2]</b>, <b>VI64[1]</b>, <b>VF32[2]</b>, <b>VF64[1]</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_VECTOR128</td>
<td>128-bit vector</td>
<td><b>VI8[16]</b>, <b>VI16[8]</b>, <b>VI32[4]</b>, <b>VI64[2]</b>, <b>VF32[4]</b>, <b>VF64[2]</b></td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include DbgEng.h) |