---
UID : NF:ntddk.PsInsertPermanentSiloContext
title : PsInsertPermanentSiloContext function
author : windows-driver-content
description : This routine inserts an object in an empty slot in a Silo.
old-location : kernel\psinsertpermanentsilocontext.htm
old-project : kernel
ms.assetid : ADBAB25B-7646-4E0E-AFD8-18B87A293674
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PsInsertPermanentSiloContext
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
req.alt-api : PsInsertPermanentSiloContext
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


# PsInsertPermanentSiloContext function
This routine inserts an object in an empty slot in a <i>Silo</i>.

## Syntax

````
NTSTATUS PsInsertPermanentSiloContext(
  _In_ PESILO Silo,
  _In_ ULONG  ContextSlot,
  _In_ PVOID  SiloContext
);
````

## Parameters

`Silo`

The silo in which the object is to be inserted. This parameter is required and it cannot be <b>NULL</b>.

`ContextSlot`

The slot in which the object is to be inserted. A slot allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine.

`SiloContext`

The object to be inserted, created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. The object must be created using the same silo as specified in the <i>Silo</i> parameter. This parameter is required and it cannot be <b>NULL</b>.


## Return Value

The following NT status codes are returned.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There are no resources in the system to perform the insert. This is an error code. 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The slot is not empty. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

## Remarks

A successful call to <b>PsInsertPermanentSiloContext</b> increments the reference count on <i>SiloContext</i>. If <b>PsInsertPermanentSiloContext</b> fails, the reference count remains unchanged. In either case, after the routine completes, the caller must call <a href="..\ntddk\nf-ntddk-psdereferencesilocontext.md">PsDereferenceSiloContext</a> to decrement the <i>SiloContext</i> object.</p>

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