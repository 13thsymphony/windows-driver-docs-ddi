---
UID : NE:ksproxy.KSPEEKOPERATION
title : KSPEEKOPERATION
author : windows-driver-content
description : .
old-location : stream\kspeekoperation.htm
old-project : stream
ms.assetid : 057E822B-0C55-4E4A-9207-48FB583E8EAF
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPEEKOPERATION, KSPEEKOPERATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ksproxy.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPEEKOPERATION
req.alt-loc : Ksproxy.h
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
req.typenames : KSPEEKOPERATION
---

# KSPEEKOPERATION Enumeration


## Syntax
````
typedef enum  { 
  KsPeekOperation_PeekOnly,
  KsPeekOperation_AddRef
} KSPEEKOPERATION;
````

## Constants

<table>

<tr>
<td>KsPeekOperation_AddRef</td>
<td></td>
</tr>

<tr>
<td>KsPeekOperation_PeekOnly</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h |