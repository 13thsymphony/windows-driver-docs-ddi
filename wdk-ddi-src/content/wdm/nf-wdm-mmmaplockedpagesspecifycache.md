---
UID: NF.wdm.MmMapLockedPagesSpecifyCache
title: MmMapLockedPagesSpecifyCache function
author: windows-driver-content
description: The MmMapLockedPagesSpecifyCache routine maps the physical pages that are described by an MDL to a virtual address, and enables the caller to specify the cache attribute that is used to create the mapping.
old-location: kernel\mmmaplockedpagesspecifycache.htm
old-project: kernel
ms.assetid: fb759043-ffdf-4edf-819b-669631927bc5
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: MmMapLockedPagesSpecifyCache
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
req.alt-api: MmMapLockedPagesSpecifyCache
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

# MmMapLockedPagesSpecifyCache function



## -description
The <b>MmMapLockedPagesSpecifyCache</b> routine maps the physical pages that are described by an MDL to a virtual address, and enables the caller to specify the cache attribute that is used to create the mapping. 



## -syntax

````
PVOID MmMapLockedPagesSpecifyCache(
  _In_     PMDLX               MemoryDescriptorList,
  _In_     KPROCESSOR_MODE     AccessMode,
  _In_     MEMORY_CACHING_TYPE CacheType,
  _In_opt_ PVOID               BaseAddress,
  _In_     ULONG               BugCheckOnFailure,
  _In_     MM_PAGE_PRIORITY    Priority
);
````


## -parameters

### -param MemoryDescriptorList [in]

A pointer to the MDL that is to be mapped. This MDL must describe physical pages that are locked down. A locked-down MDL can be built by the <a href="kernel.mmprobeandlockpages">MmProbeAndLockPages</a> or <a href="kernel.mmallocatepagesformdlex">MmAllocatePagesForMdlEx</a> routine. For mappings to user space, MDLs that are built by the <a href="kernel.mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a> routine can be used.


### -param AccessMode [in]

Specifies the access mode in which to map the MDL: <b>KernelMode</b> or <b>UserMode</b>. Almost all drivers should use <b>KernelMode</b>.


### -param CacheType [in]

Specifies a <a href="kernel.memory_caching_type">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the MDL. For more information, see the following Remarks section.


### -param BaseAddress [in, optional]

If <i>AccessMode</i> = <b>UserMode</b>, this parameter specifies the starting user virtual address to map the MDL to, or set to <b>NULL</b> to allow the system to choose the starting address. The system might round down the requested address to fit address boundary requirements, so callers must check the return value.


### -param BugCheckOnFailure [in]

Specifies the behavior of the routine for <i>AccessMode</i> = <b>KernelMode</b> if the MDL cannot be mapped because of low system resources. If <b>TRUE</b>, the system issues a bug check. If <b>FALSE</b>, the routine returns <b>NULL</b>. Drivers must set this parameter to <b>FALSE</b>. 


### -param Priority [in]

An <b>MM_PAGE_PRIORITY</b> value that indicates the importance of success when page table entries (PTEs) are scarce. Starting with Windows 8, the specified priority value can be bitwise-ORed with the <b>MdlMappingNoWrite</b> or <b>MdlMappingNoExecute</b> flags to specify memory in which writes or instruction execution are disabled. For more information about the possible values for <i>Priority</i>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>. 


## -returns
<b>MmMapLockedPagesSpecifyCache</b> returns the starting address of the mapped pages. If the pages cannot be mapped and <i>BugCheckOnFailure</i> is <b>FALSE</b>, the routine returns <b>NULL</b>.


## -remarks
Use <a href="kernel.mmunmaplockedpages">MmUnmapLockedPages</a> to unmap the physical pages that were mapped by <b>MmMapLockedPagesSpecifyCache</b>.

If <i>AccessMode</i> is <b>KernelMode</b>, and if <b>MmMapLockedPagesSpecifyCache</b> cannot map the specified pages, the routine returns <b>NULL</b> (if <i>BugCheckOnFailure</i> = <b>FALSE</b>), or the operating system issues a bug check (if <i>BugCheckOnFailure</i> = <b>TRUE</b>).

If <i>AccessMode</i> is <b>UserMode</b>, be aware of the following details:

If the specified pages cannot be mapped, the routine raises an exception. Callers that specify <b>UserMode</b> must wrap the call to <b>MmMapLockedPagesSpecifyCache</b> in a <b>try/except</b> block. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>.

The routine returns a user address that is valid in the context of the process in which the driver is running. For example, if a 64-bit driver is running in the context of a 32-bit application, the buffer is mapped to an address in the 32-bit address range of the application. 

A non-executable mapping is always created when <i>AccessMode</i> is <b>UserMode</b>. Therefore, using the <b>MdlMappingNoExecute</b> flag with the <i>Priority</i> parameter is unnecessary in this scenario. However, the <b>MdlMappingNoWrite</b> flag can still be used with the <i>Priority</i> parameter in this scenario to request a read-only mapping.

The non-executable protection of the mapping and any write protection of the mapping specified by  using the <b>MdlMappingNoWrite</b> flag with the <i>Priority</i> parameter cannot be changed by code that is running in user mode. For example, if a driver maps some pages into a user process and specifies the <b>MdlMappingNoWrite</b> flag, the system guarantees that the process cannot modify the pages.

The routine uses the <i>CacheType</i> parameter only if the pages that are described by the MDL do not already have a cache type associated with them. However, in nearly all cases, the pages already have an associated cache type, and this cache type is used by the new mapping. An exception to this rule is for pages that are allocated by <a href="kernel.mmallocatepagesformdl">MmAllocatePagesForMdl</a>, which do not have a specific cache type associated with them. For such pages, the <i>CacheType</i> parameter determines the cache type of the mapping. 

A driver must not try to create more than one system-address-space mapping for an MDL. Additionally, because an MDL that is built by the <a href="kernel.mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a> routine is already mapped to the system address space, a driver must not try to map this MDL into the system address space again by using the <b>MmMapLockedPagesSpecifyCache</b> routine (although creating user-address-space mappings is allowed). If it is not known whether a locked-down MDL already has a system-address-space mapping, a driver can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a> macro instead of <b>MmMapLockedPagesSpecifyCache</b>. If the MDL is already mapped into the system address space, <b>MmGetSystemAddressForMdlSafe</b> will return the existing system-address-space mapping instead of creating a new mapping.

If <i>AccessMode</i> is <b>UserMode</b>, the caller must be running at IRQL &lt;= APC_LEVEL. If <i>AccessMode</i> is <b>KernelMode</b>, the caller must be running at IRQL &lt;= DISPATCH_LEVEL. 


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
<a href="kernel.mmallocatepagesformdl">MmAllocatePagesForMdl</a>
</dt>
<dt>
<a href="kernel.mmallocatepagesformdlex">MmAllocatePagesForMdlEx</a>
</dt>
<dt>
<a href="kernel.mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>
</dt>
<dt>
<a href="kernel.mmprobeandlockpages">MmProbeAndLockPages</a>
</dt>
<dt>
<a href="kernel.mmunmaplockedpages">MmUnmapLockedPages</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmMapLockedPagesSpecifyCache routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

