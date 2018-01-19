---
UID : NE:ehstorioctl._PDO_CAPS
title : _PDO_CAPS
author : windows-driver-content
description : This enumeration describes the capabilities of Physical Device Objects (PDOs).
old-location : storage\pdo_caps.htm
old-project : storage
ms.assetid : 78b6f3c7-bb42-4e93-8128-28b6f8e11dda
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _PDO_CAPS, PDO_CAPS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ehstorioctl.h
req.include-header : EhStorIoctl.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PDO_CAPS
req.alt-loc : EhStorIoctl.h
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
req.typenames : PDO_CAPS
---

# _PDO_CAPS Enumeration
This enumeration describes the capabilities of Physical Device Objects (PDOs).

## Syntax
````
typedef enum _PDO_CAPS { 
  PDO_CAPABILITY_UNDEFINED     = 0,
  PDO_CAPABILITY_INC512_SET    = 1,
  PDO_CAPABILITY_INC512_CLEAR  = 2
} PDO_CAPS;
````

## Constants

<table>

<tr>
<td>PDO_CAPABILITY_INC512_CLEAR</td>
<td>Command data block size granularity of 1 byte is supported.</td>
</tr>

<tr>
<td>PDO_CAPABILITY_INC512_SET</td>
<td>Command data block size granularity of 512 bytes is supported.</td>
</tr>

<tr>
<td>PDO_CAPABILITY_UNDEFINED</td>
<td>Command data block size granularity is undefined.</td>
</tr>
</table>

## Remarks

A silo must support either PDO_CAPABILITY_INC512_SET or PDO_CAPABILITY_INC512_CLEAR. It may also indicate that both values are supported by returning a logical OR of these two bits.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |