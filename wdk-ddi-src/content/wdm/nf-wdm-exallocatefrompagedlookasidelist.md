---
UID: NF.wdm.ExAllocateFromPagedLookasideList
title: ExAllocateFromPagedLookasideList function
author: windows-driver-content
description: The ExAllocateFromPagedLookasideList routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry.
old-location: kernel\exallocatefrompagedlookasidelist.htm
old-project: kernel
ms.assetid: f0c86720-4914-47b1-abb1-151196cc2a68
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ExAllocateFromPagedLookasideList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExAllocateFromPagedLookasideList
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# ExAllocateFromPagedLookasideList function



## -description
The <b>ExAllocateFromPagedLookasideList</b> routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry. 


## -syntax

````
PVOID ExAllocateFromPagedLookasideList(
  _Inout_ PPAGED_LOOKASIDE_LIST Lookaside
);
````


## -parameters

### -param Lookaside [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="kernel.exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>. 

## -returns
<b>ExAllocateFromPagedLookasideList</b> returns a pointer to an entry if one can be allocated. Otherwise, it returns <b>NULL</b>.

## -remarks
If the given lookaside list is not empty, <b>ExAllocateFromPagedLookasideList</b> removes the first entry from the list and returns a pointer to this entry. Otherwise, <b>ExAllocateFromPagedLookasideList</b> either calls the <i>Allocate</i> routine specified at list initialization or <a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a> to return an entry pointer.

The caller can then set up the returned entry with any caller-determined data. The caller should release each entry with <a href="kernel.exfreetopagedlookasidelist">ExFreeToPagedLookasideList</a> when it is no longer in use. 

Because the entries in a paged lookaside list are allocated from pageable memory, they must not be accessed at an IRQL &gt;= DISPATCH_LEVEL. You can use <a href="kernel.exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a> to create a lookaside list with non-pageable entries.

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExAllocateFromPagedLookasideList</b>.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 2000.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="kernel.exfreetopagedlookasidelist">ExFreeToPagedLookasideList</a>
</dt>
<dt>
<a href="kernel.exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocateFromPagedLookasideList routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
