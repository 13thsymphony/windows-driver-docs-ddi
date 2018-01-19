---
UID : NE:rilapitypes.RILPHONEBOOKANSOPERATION
title : RILPHONEBOOKANSOPERATION
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilphonebookansoperation_2.htm
old-project : netvista
ms.assetid : ce1d2d09-64a3-40a9-b24b-66edbd34d637
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILPHONEBOOKANSOPERATION, RILPHONEBOOKANSOPERATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : rilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILPHONEBOOKANSOPERATION
req.alt-loc : rilapitypes.h
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
req.typenames : RILPHONEBOOKANSOPERATION
req.product : Windows 10 or later.
---

# RILPHONEBOOKANSOPERATION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILPHONEBOOKANSOPERATION { 
  RIL_PHONEBOOK_ANSMODIFIED,
  RIL_PHONEBOOK_ANSDELETED,
  RIL_PHONEBOOK_MAX
} RILPHONEBOOKANSOPERATION;
````

## Constants

<table>

<tr>
<td>RIL_PHONEBOOK_ANSDELETED</td>
<td></td>
</tr>

<tr>
<td>RIL_PHONEBOOK_ANSMODIFIED</td>
<td></td>
</tr>

<tr>
<td>RIL_PHONEBOOK_MAX</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |