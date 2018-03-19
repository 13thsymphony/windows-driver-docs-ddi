---
UID: NF:fltkernel.FltCloseSectionForDataScan
title: FltCloseSectionForDataScan function
author: windows-driver-content
description: The FltCloseSectionForDataScan routine closes a section object associated with a file stream.
old-location: ifsk\fltclosesectionfordatascan.htm
old-project: ifsk
ms.assetid: 2B3C52FD-80D7-4ECA-9B33-7916FB47B0B2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltCloseSectionForDataScan, FltCloseSectionForDataScan routine [Installable File System Drivers], fltkernel/FltCloseSectionForDataScan, ifsk.fltclosesectionfordatascan
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCloseSectionForDataScan routine is available starting with  Windows 8.
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCloseSectionForDataScan
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltCloseSectionForDataScan function
The <b>FltCloseSectionForDataScan</b> routine closes a section object associated with a file stream.

## Syntax

````
NTSTATUS FltCloseSectionForDataScan(
  _In_ PFLT_CONTEXT SectionContext
);
````

## Parameters

`SectionContext`

A pointer to the section context to close.


## Return Value

<b>FltCloseSectionForDataScan</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The section context was not properly created. An allocated section context must first be passed to <a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a>. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The section context is already closed.

</td>
</tr>
</table>

## Remarks

Minifilters use the <b>FltCloseSectionForDataScan</b> routine to deallocate  and remove a section context from a file object. All previously allocated section contexts passed to <a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a> must be passed to <b>FltCloseSectionForDataScan</b>. Otherwise, minifilters can call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> if the section context was allocated with <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a> but no section was created with  <b>FltCreateSectionForDataScan</b>.

After <b>FltCloseSectionForDataScan</b> returns, operations that conflict with the section  described by <i>SectionContext</i> will not be synchronized by the filter manager.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FltCloseSectionForDataScan routine is available starting with  Windows 8.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a>