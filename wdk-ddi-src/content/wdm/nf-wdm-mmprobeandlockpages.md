---
UID: NF.wdm.MmProbeAndLockPages
title: MmProbeAndLockPages function
author: windows-driver-content
description: The MmProbeAndLockPages routine probes the specified virtual memory pages, makes them resident, and locks them in memory.
old-location: kernel\mmprobeandlockpages.htm
old-project: kernel
ms.assetid: d958004f-1730-412d-be75-e51628e6fcdc
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: MmProbeAndLockPages
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
req.alt-api: MmProbeAndLockPages
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
req.product: Windows 10 or later.
---

# MmProbeAndLockPages function



## -description
The <b>MmProbeAndLockPages</b> routine probes the specified virtual memory pages, makes them resident, and locks them in memory.



## -syntax

````
VOID MmProbeAndLockPages(
  _Inout_ PMDLX           MemoryDescriptorList,
  _In_    KPROCESSOR_MODE AccessMode,
  _In_    LOCK_OPERATION  Operation
);
````


## -parameters

### -param MemoryDescriptorList [in, out]

A pointer to an MDL that specifies a virtual memory buffer. If the routine successfully locks the pages in memory, the MDL is updated to describe the underlying physical pages.


### -param AccessMode [in]

The access mode in which to probe the arguments, either <b>KernelMode</b> or <b>UserMode</b>.


### -param Operation [in]

The type of operation for which the caller wants the access rights probed and the pages locked. Set this parameter to <b>IoReadAccess</b>, <b>IoWriteAccess</b>, or <b>IoModifyAccess</b>. <b>IoReadAccess</b> indicates that the driver can examine the contents of the buffer but cannot change the contents. <b>IoWriteAccess</b> and <b>IoModifyAccess</b>, which are equivalent, indicate that the driver has both read and write access to the buffer.


## -returns
None


## -remarks
The highest-level driver in a chain of layered drivers that use direct I/O calls this routine. Drivers that use buffered I/O never call <b>MmProbeAndLockPages</b>.

<b>MmProbeAndLockPages</b> performs the following operations:

If the specified memory range is paged to a backing store (disk, network, and so on), <b>MmProbeAndLockPages</b> makes it resident.

The routine then confirms that the pages permit the operation specified by the <i>Operation</i> parameter.

If the memory range permits the specified operation, the routine locks the pages in memory so that they cannot be paged out. Use the <a href="kernel.mmunlockpages">MmUnlockPages</a> routine to unlock the pages.

Finally, the routine updates the <a href="wdkgloss.p#wdkgloss.page_frame_number__pfn_#wdkgloss.page_frame_number__pfn_"><i>page frame number</i></a> (PFN) array in the MDL to describe the locked physical pages.

A successful call to <b>MmProbeAndLockPages</b> locks the pages in an MDL and sets the MDL structure to the locked state. Every such call must be matched by a corresponding call to <b>MmUnlockPages</b> that unlocks the pages and sets the MDL to the unlocked state. After an <b>MmProbeAndLockPages</b> call sets an MDL to the locked state, a second call to MmProbeAndLockPages to lock the same MDL is not allowed until <b>MmUnlockPages</b> is first called to unlock the MDL.

If two or more MDLs describe the same physical page, the page can be locked multiple times—once for each MDL. The page is unlocked when the last MDL is set to the unlocked state.

A routine such as <a href="kernel.mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a> or <a href="kernel.iobuildpartialmdl">IoBuildPartialMdl</a> updates an MDL to describe pages that are either nonpageable or already locked. A call to <b>MmProbeAndLockPages</b> or <b>MmUnlockPages</b> to lock or unlock such an MDL is not allowed.

Calls to <b>MmProbeAndLockPages</b> must be enclosed in a <b>try/except</b> block. If the pages do not support the specified operation, the routine raises the STATUS_ACCESS_VIOLATION or other exceptions. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>.

Callers of <b>MmProbeAndLockPages</b> must be running at IRQL &lt;= APC_LEVEL for pageable addresses, or at IRQL &lt;= DISPATCH_LEVEL for nonpageable addresses.

This routine does not provide any guarantees about the virtual address that describes these pages (that is, the virtual address might be unmapped, reused, and so on). However, the physical pages are guaranteed to be locked on successful return.


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
See Remarks section.

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iobuildpartialmdl">IoBuildPartialMdl</a>
</dt>
<dt>
<a href="kernel.mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a>
</dt>
<dt>
<a href="kernel.mmunlockpages">MmUnlockPages</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmProbeAndLockPages routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

