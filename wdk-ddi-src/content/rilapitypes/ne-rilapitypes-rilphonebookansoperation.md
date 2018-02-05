---
UID : NE:rilapitypes.RILPHONEBOOKANSOPERATION
title : RILPHONEBOOKANSOPERATION
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilphonebookansoperation_2.htm
old-project : netvista
ms.assetid : ce1d2d09-64a3-40a9-b24b-66edbd34d637
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilphonebookansoperation_2, rilapitypes/RIL_PHONEBOOK_ANSDELETED, RIL_PHONEBOOK_MAX, RILPHONEBOOKANSOPERATION enumeration [Network Drivers Starting with Windows Vista], RIL_PHONEBOOK_ANSDELETED, rilapitypes/RILPHONEBOOKANSOPERATION, rilapitypes/RIL_PHONEBOOK_MAX, RIL_PHONEBOOK_ANSMODIFIED, RILPHONEBOOKANSOPERATION, rilapitypes/RIL_PHONEBOOK_ANSMODIFIED
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
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
<td>RIL_PHONEBOOK_ANSADDED</td>
<td></td>
</tr>

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
| **Header** | rilapitypes.h |