---
UID: NF:dbgeng.IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets
title: IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets method
author: windows-driver-content
description: The GetVirtualTranslationPhysicalOffsets method returns the physical addresses of the system paging structures at different levels of the paging hierarchy.
old-location: debugger\getvirtualtranslationphysicaloffsets.htm
old-project: debugger
ms.assetid: 40438ee7-2e58-4048-8739-75f21179c22c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetVirtualTranslationPhysicalOffsets method [Windows Debugging], GetVirtualTranslationPhysicalOffsets method [Windows Debugging], IDebugDataSpaces2 interface, GetVirtualTranslationPhysicalOffsets method [Windows Debugging], IDebugDataSpaces3 interface, GetVirtualTranslationPhysicalOffsets method [Windows Debugging], IDebugDataSpaces4 interface, GetVirtualTranslationPhysicalOffsets,IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces2, IDebugDataSpaces2 interface [Windows Debugging], GetVirtualTranslationPhysicalOffsets method, IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces3 interface [Windows Debugging], GetVirtualTranslationPhysicalOffsets method, IDebugDataSpaces3::GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces4 interface [Windows Debugging], GetVirtualTranslationPhysicalOffsets method, IDebugDataSpaces4::GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces_661959c5-a514-4651-8eaa-fd4c4fb94bd7.xml, dbgeng/IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets, dbgeng/IDebugDataSpaces3::GetVirtualTranslationPhysicalOffsets, dbgeng/IDebugDataSpaces4::GetVirtualTranslationPhysicalOffsets, debugger.getvirtualtranslationphysicaloffsets
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets
-	IDebugDataSpaces3.GetVirtualTranslationPhysicalOffsets
-	IDebugDataSpaces4.GetVirtualTranslationPhysicalOffsets
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetVirtualTranslationPhysicalOffsets method
The <b>GetVirtualTranslationPhysicalOffsets</b> method returns the physical addresses of the system paging structures at different levels of the paging hierarchy.

## Syntax

````
HRESULT GetVirtualTranslationPhysicalOffsets(
  [in]            ULONG64  Virtual,
  [out, optional] PULONG64 Offsets,
  [in]            ULONG    OffsetsSize,
  [out, optional] PULONG   Levels
);
````

## Parameters

`Virtual`

Specifies the location in the target's virtual address space to translate.

`Offsets`

Receives the physical addresses for the system paging structures.  If it is set to <b>NULL</b>, this information is not returned.

`OffsetsSize`

Specifies the number of elements the array <i>Offsets</i> holds.  This is the maximum number of addresses that will be returned.

`Levels`

Receives the number of levels in the paging hierarchy for the specified address.  If this is <b>NULL</b>, this information is not returned.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_NO_PAGEFILE)</b></dt>
</dl>
</td>
<td width="60%">
No physical page containing the specified address could be found.

</td>
</tr>
</table>

## Remarks

This method is only available in kernel-mode debugging.

Translating a virtual address to a physical address requires Windows  to walk down the paging hierarchy.  At each level it reads paging information from physical memory.  This method returns the offsets for these physical pages.  The number of levels in the paging hierarchy may be different for different addresses.

The address at the last level of the hierarchy is the physical address corresponding to the specified virtual address.  This is what <a href="https://msdn.microsoft.com/library/windows/hardware/ff560335">VirtualToPhysical</a> would return.

For details on how virtual addresses are translated into physical addresses, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |