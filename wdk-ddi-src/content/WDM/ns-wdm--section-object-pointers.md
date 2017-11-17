---
UID: NS.wdm._SECTION_OBJECT_POINTERS
title: SECTION_OBJECT_POINTERS
author: windows-driver-content
description: The SECTION_OBJECT_POINTERS structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream.
old-location: kernel\section_object_pointers.htm
ms.assetid: ce867f4f-f091-4a85-96b8-7da6b528a6cc
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available in all versions of Windows that Microsoft supports.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SECTION_OBJECT_POINTERS
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
ms.keywords: SECTION_OBJECT_POINTERS, SECTION_OBJECT_POINTERS
req.iface: 
req.product: Windows 10 or later.
---

# SECTION_OBJECT_POINTERS structure



## -description
<p>The <b>SECTION_OBJECT_POINTERS</b> structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream.</p>


## -syntax

````
typedef struct _SECTION_OBJECT_POINTERS {
  PVOID DataSectionObject;
  PVOID SharedCacheMap;
  PVOID ImageSectionObject;
} SECTION_OBJECT_POINTERS, *PSECTION_OBJECT_POINTERS;
````


## -struct-fields
<dl>

### -field <b>DataSectionObject</b>

<dd>
<p>Opaque pointer to a data section object (that is, a <b>CONTROL_AREA</b> structure) that is used to track state information for a data file stream. Memory manager sets this member when the operating system first caches the data stream. A <b>NULL</b> value indicates that the data stream is <u>currently</u> not in memory; this value, however, can change at any time.</p>
</dd>

### -field <b>SharedCacheMap</b>

<dd>
<p>Opaque pointer to a cache map object (that is, a <b>SHARED_CACHE_MAP</b> structure) that is used to track views that are mapped to the data file stream. Cache manager sets this member when the operating system first caches the stream. A <b>NULL</b> value indicates that the data stream is <pre class="syntax">currently</pre> not cached; this value, however, can change at any time.</p>
</dd>

### -field <b>ImageSectionObject</b>

<dd>
<p>Opaque pointer to an image section object (that is, a <b>CONTROL_AREA</b> structure) that is used to track state information for an executable file stream. Memory manager sets this member whenever an executable image section is created for the stream. A <b>NULL</b> value indicates that the executable image is <u>currently</u> not in memory; this value, however, can change at any time. </p>
</dd>
</dl>

## -remarks
<p>The <b>SECTION_OBJECT_POINTERS</b> structure links a file object to a file stream's section object. That is, through its members, the <b>SECTION_OBJECT_POINTERS</b> structure connects a particular file object to virtual memory control structures that keep track of the stream's contents when they are in memory, and allow the operating system to fetch those contents when they are not. </p>

<p>There is a one-to-one relationship between a <b>SECTION_OBJECT_POINTERS</b> structure and a file stream. Multiple file objects can be associated with a particular file stream, each representing an open instance of the stream. However, only one <b>SECTION_OBJECT_POINTERS</b> structure can be associated with a given stream. If there are multiple file objects for a stream, the <b>SectionObjectPointer</b> member for all file objects must point to the same <b>SECTION_OBJECT_POINTERS</b> structure (that is associated with the stream).</p>

<p>For the <u>first</u> file stream open request, the file system or the redirector driver must:</p>

<p>Allocate a <b>SECTION_OBJECT_POINTERS</b> structure from a nonpaged pool.</p>

<p>Initialize all members of the allocated <b>SECTION_OBJECT_POINTERS</b> structure to <b>NULL</b>.</p>

<p>  Set the <b>SectionObjectPointer</b> member of the associate file object to point to the initialized <b>SECTION_OBJECT_POINTERS</b> structure.</p>

<p>For <u>subsequent</u> open requests to the <u>same</u> file stream, the file system or the redirector driver must set the <b>SectionObjectPointer</b> member of the associated file object to point to the previously allocated <b>SECTION_OBJECT_POINTERS</b> structure for the file stream.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in all versions of Windows that Microsoft supports.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>
</dt>
<dt>
<a href="ifsk.the_fobx_structure">FOBX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549198">IoGetDeviceObjectPointer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549808">MmFlushImageSection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SECTION_OBJECT_POINTERS structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
