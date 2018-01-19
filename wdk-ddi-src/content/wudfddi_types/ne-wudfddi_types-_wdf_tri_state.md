---
UID : NE:wudfddi_types._WDF_TRI_STATE
title : _WDF_TRI_STATE
author : windows-driver-content
description : The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.
old-location : wdf\wdf_tri_state.htm
old-project : wdf
ms.assetid : 8ea6e373-225d-4fcd-abcf-c19b07f9f5d8
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_TRI_STATE, WDF_TRI_STATE, *PWDF_TRI_STATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wudfddi_types.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 1.11
req.alt-api : WDF_TRI_STATE
req.alt-loc : wdftypes.h,wudfddi_types.h
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
req.typenames : WDF_TRI_STATE, *PWDF_TRI_STATE
req.product : Windows 10 or later.
---

# _WDF_TRI_STATE Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.

## Syntax
````
typedef enum _WDF_TRI_STATE { 
  WdfFalse       = FALSE,
  WdfTrue        = TRUE,
  WdfUseDefault  = 2
} WDF_TRI_STATE, *PWDF_TRI_STATE;
````

## Constants

<table>

<tr>
<td>WdfFalse</td>
<td>The meaning of this enumerator is specific to its use as a structure member or function parameter.</td>
</tr>

<tr>
<td>WdfTrue</td>
<td>The meaning of this enumerator is specific to its use as a structure member or function parameter.</td>
</tr>

<tr>
<td>WdfUseDefault</td>
<td>The meaning of this enumerator is specific to its use as a structure member or function parameter.</td>
</tr>
</table>

## Remarks

The WDF_TRI_STATE enumeration type is available in version 1.0 and later versions of KMDF.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi_types.h (include Wdf.h) |