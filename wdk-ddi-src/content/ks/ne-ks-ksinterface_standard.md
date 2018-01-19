---
UID : NE:ks.KSINTERFACE_STANDARD
title : KSINTERFACE_STANDARD
author : windows-driver-content
description : .
old-location : stream\ksinterface_standard.htm
old-project : stream
ms.assetid : B000E3BD-28FA-454E-A598-3670B5FCD3DD
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSINTERFACE_STANDARD, KSINTERFACE_STANDARD
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ks.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSINTERFACE_STANDARD
req.alt-loc : Ks.h
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
req.typenames : KSINTERFACE_STANDARD
---

# KSINTERFACE_STANDARD Enumeration


## Syntax
````
typedef enum  { 
  KSINTERFACE_STANDARD_STREAMING,
  KSINTERFACE_STANDARD_LOOPED_STREAMING,
  KSINTERFACE_STANDARD_CONTROL
} KSINTERFACE_STANDARD;
````

## Constants

<table>

<tr>
<td>KSINTERFACE_STANDARD_CONTROL</td>
<td>Reserved for system use.</td>
</tr>

<tr>
<td>KSINTERFACE_STANDARD_LOOPED_STREAMING</td>
<td></td>
</tr>

<tr>
<td>KSINTERFACE_STANDARD_STREAMING</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |