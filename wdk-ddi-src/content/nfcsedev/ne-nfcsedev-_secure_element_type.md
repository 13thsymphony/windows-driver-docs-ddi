---
UID : NE:nfcsedev._SECURE_ELEMENT_TYPE
title : _SECURE_ELEMENT_TYPE
author : windows-driver-content
description : Indicates the type of a secure element.
old-location : nfpdrivers\_secure_element_type.htm
old-project : nfpdrivers
ms.assetid : 118B63D1-713A-4F8C-B97A-53BB6D0B819E
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : _SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : nfcsedev.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE
req.alt-loc : nfcsedev.h
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
req.typenames : "*PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE"
---

# _SECURE_ELEMENT_TYPE Enumeration
Indicates the type of a secure element.

## Syntax
````
typedef enum _SECURE_ELEMENT_TYPE { 
  Integrated  = 0,
  External    = 1,
  DeviceHost  = 2
} SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE;
````

## Constants

<table>

<tr>
<td>DeviceHost</td>
<td>Separate HCE-based secure element.</td>
</tr>

<tr>
<td>External</td>
<td>Separate UICC-based secure element.</td>
</tr>

<tr>
<td>Integrated</td>
<td>Integrated secure element.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | nfcsedev.h |