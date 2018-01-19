---
UID : NE:ks.KSLIST_ENTRY_LOCATION
title : KSLIST_ENTRY_LOCATION
author : windows-driver-content
description : .
old-location : stream\kslist_entry_location.htm
old-project : stream
ms.assetid : C2047F4D-6D24-432B-98F1-EA00D88E3860
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSLIST_ENTRY_LOCATION, KSLIST_ENTRY_LOCATION
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
req.alt-api : KSLIST_ENTRY_LOCATION
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
req.typenames : KSLIST_ENTRY_LOCATION
---

# KSLIST_ENTRY_LOCATION Enumeration


## Syntax
````
typedef enum  { 
  KsListEntryTail,
  KsListEntryHead
} KSLIST_ENTRY_LOCATION;
````

## Constants

<table>

<tr>
<td>KsListEntryHead</td>
<td></td>
</tr>

<tr>
<td>KsListEntryTail</td>
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