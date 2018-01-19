---
UID : NF:ntddk.PsMakeSiloContextPermanent
title : PsMakeSiloContextPermanent function
author : windows-driver-content
description : This routine makes the slot in a silo instance read-only, allowing the object in the slot to be retrieved without affecting the reference count on that object.
old-location : kernel\psmakesilocontextpermanent.htm
old-project : kernel
ms.assetid : 74BE4FF9-0342-4942-A58F-9C6D5F76E5F0
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PsMakeSiloContextPermanent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1607
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PsMakeSiloContextPermanent
req.alt-loc : ntddk.h
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
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsMakeSiloContextPermanent function
This routine makes the slot in a silo instance read-only, allowing the object in the slot to be retrieved without affecting the reference count on that object.

## Syntax

````
NTSTATUS PsMakeSiloContextPermanent(
  _In_ PESILO Silo,
  _In_ ULONG  ContextSlot
);
````

## Parameters

`Silo`

The silo in which the slot resides. This parameter is required and it cannot be <b>NULL</b>.

`ContextSlot`

The slot to make read-only. The slot must be previously allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine.


## Return Value

The following NT status codes are returned.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The slot does not contain a valid object. This is an error code.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The slot has not been allocated. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

## Remarks

Before calling this routine, the slot must contain a valid object. After it completes, the <a href="..\ntddk\nf-ntddk-psreplacesilocontext.md">PsReplaceSiloContext</a> and <a href="..\ntddk\nf-ntddk-psremovesilocontext.md">PsRemoveSiloContext</a> routines will fail with <b>STATUS_NOT_SUPPORTED</b>. </p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |