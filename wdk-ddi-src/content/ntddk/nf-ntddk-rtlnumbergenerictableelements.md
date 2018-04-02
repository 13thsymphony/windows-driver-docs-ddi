---
UID: NF:ntddk.RtlNumberGenericTableElements
title: RtlNumberGenericTableElements function
author: windows-driver-content
description: The RtlNumberGenericTableElements routine returns the number of elements in a generic table.
old-location: ifsk\rtlnumbergenerictableelements.htm
old-project: ifsk
ms.assetid: 7dea199f-ef98-4f7b-a3e4-de52fc23c8ef
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlNumberGenericTableElements, RtlNumberGenericTableElements routine [Installable File System Drivers], ifsk.rtlnumbergenerictableelements, ntddk/RtlNumberGenericTableElements, rtlref_f12988ba-01c3-4a34-8967-aafaf5b605f8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlNumberGenericTableElements
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlNumberGenericTableElements function
The <b>RtlNumberGenericTableElements</b> routine returns the number of elements in a generic table.

## Syntax

```
NTSYSAPI ULONG RtlNumberGenericTableElements(
  PRTL_GENERIC_TABLE Table
);
```

## Parameters

`Table`

Pointer to the generic table (<a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>.


## Return Value

<b>RtlNumberGenericTableElements</b> returns the number of elements that are currently stored in the table.

## Remarks

Callers of the <i>Rtl..GenericTable</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406522">RtlNumberGenericTableElementsAvl</a> routine instead of <b>RtlNumberGenericTableElements</b>. In the call to <b>RtlNumberGenericTableElementsAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlNumberGenericTableElements</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL (see Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553046">RtlIsGenericTableEmpty</a>