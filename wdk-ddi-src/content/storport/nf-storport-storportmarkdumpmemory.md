---
UID : NF:storport.StorPortMarkDumpMemory
title : StorPortMarkDumpMemory function
author : windows-driver-content
description : A miniport should mark memory used for the dump file or the hibernation file.
old-location : storage\storportmarkdumpmemory.htm
old-project : storage
ms.assetid : DE17FF55-A573-41FE-8979-1DB32AD5B7C0
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortMarkDumpMemory
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : StorPortMarkDumpMemory
req.alt-loc : Storport.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Any
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortMarkDumpMemory function
A miniport should mark  memory used for the dump file or the hibernation file. Marked memory is retained and remains valid after a resume from hibernation operation. The memory  to mark is specified by an address and range length in a call to <b>StorPortMarkDumpMemory</b>.

## Syntax

````
ULONG StorPortMarkDumpMemory(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Address,
  _In_ PVOID Length,
  _In_ PVOID Flags
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`Address`

The starting address of the memory range to mark.

`Length`

The length of the marked memory range.

`Flags`

Dump memory marking flags. The <i>Flags</i> parameter must be 0 or contain only the following value.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>


## Return Value

<b>StorPortMarkDumpMemory</b> returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that the routine set the unit attributes successfully.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid flag value was specified in the <i>Flags</i> parameter.

## Remarks

The <b>StorPortMarkDumpMemory</b> routine must only be called by a miniport driver in its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> or <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routines.

If <i>Length</i> = 0, the entire section containing <i>Address</i> is marked.

Miniport drivers should call <b>StorPortMarkDumpMemory</b> to ensure that the memory used by the miniport to generate either the dump file or the hibernation file is identified. At a minimum, miniports should call <b>StorPortMarkDumpMemory</b> when the <b>DumpMode</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is set to either <b>DUMP_MODE_MARK_MEMORY</b> or <b>DUMP_MODE_HIBER</b>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | Any |
| **DDI compliance rules** |  |