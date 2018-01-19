---
UID : NE:winspool.BIDI_TYPE
title : BIDI_TYPE
author : windows-driver-content
description : The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation.
old-location : print\bidi_type.htm
old-project : print
ms.assetid : ebb79ad6-91a1-4bdf-a6f6-7e04ed2358d9
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : BIDI_TYPE, BIDI_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : winspool.h
req.include-header : Winspool.h
req.target-type : Windows
req.target-min-winverclnt : This enumeration is available in Windows XP and later operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BIDI_TYPE
req.alt-loc : winspool.h
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
req.typenames : BIDI_TYPE
req.product : Windows 10 or later.
---

# BIDI_TYPE Enumeration
The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation.

## Syntax
````
typedef enum  { 
  BIDI_NULL    = 0,
  BIDI_INT     = 1,
  BIDI_FLOAT   = 2,
  BIDI_BOOL    = 3,
  BIDI_STRING  = 4,
  BIDI_TEXT    = 5,
  BIDI_ENUM    = 6,
  BIDI_BLOB    = 7
} BIDI_TYPE;
````

## Constants

<table>

<tr>
<td>BIDI_BLOB</td>
<td>Indicates that the bidi data is binary data.</td>
</tr>

<tr>
<td>BIDI_BOOL</td>
<td>Indicates that the bidi data is either <b>TRUE</b> or <b>FALSE</b>.</td>
</tr>

<tr>
<td>BIDI_ENUM</td>
<td>Indicates that the bidi data value is a Unicode string.</td>
</tr>

<tr>
<td>BIDI_FLOAT</td>
<td>Indicates that the bidi data is a floating-point number.</td>
</tr>

<tr>
<td>BIDI_INT</td>
<td>Indicates that the bidi data is an integer.</td>
</tr>

<tr>
<td>BIDI_NULL</td>
<td>Indicates that there is no data.</td>
</tr>

<tr>
<td>BIDI_STRING</td>
<td>Indicates that the bidi data is a Unicode character string.</td>
</tr>

<tr>
<td>BIDI_TEXT</td>
<td>Indicates that the bidi data is a nonlocalizable Unicode string.</td>
</tr>
</table>

## Remarks

The following correspondence applies between Simple Network Management Protocol (SNMP) types and bidi types defined in the BIDI_TYPE enumeration.

SNMP_SYNTAX_CNTR32

SNMP_SYNTAX_GAUGE32

SNMP_SYNTAX_INT

SNMP_SYNTAX_TIMETICKS

SNMP_SYNTAX_UINT32

BIDI_BOOL

BIDI_INT

SNMP_SYNTAX_IPADDR

SNMP_SYNTAX_OCTETS

SNMP_SYNTAX_OID

BIDI_ENUM

BIDI_STRING

BIDI_TEXT

SNMP_SYNTAX_CNTR64

SNMP_SYNTAX_OPAQUE

BIDI_BLOB

(none)

BIDI_FLOAT

See the smiValue structure in the Microsoft Windows SDK documentation for descriptions of the WinSNMP data types.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winspool.h (include Winspool.h) |