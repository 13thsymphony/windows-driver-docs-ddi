---
UID: NS.NTIFS._FSRTL_PER_FILEOBJECT_CONTEXT
title: _FSRTL_PER_FILEOBJECT_CONTEXT
author: windows-driver-content
description: The opaque FSRTL_PER_FILEOBJECT_CONTEXT structure is used by the operating system to track file system filter-driver-defined context information structures for a file object.
old-location: ifsk\fsrtl_per_fileobject_context.htm
old-project: ifsk
ms.assetid: f9d6f957-5878-45ca-86a3-1c62f2a52e65
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FSRTL_PER_FILEOBJECT_CONTEXT, *PFSRTL_PER_FILEOBJECT_CONTEXT, FSRTL_PER_FILEOBJECT_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FSRTL_PER_FILEOBJECT_CONTEXT
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _FSRTL_PER_FILEOBJECT_CONTEXT structure



## -description
The opaque <b>FSRTL_PER_FILEOBJECT_CONTEXT </b>structure is used by the operating system to track file system filter-driver-defined context information structures for a file object.



## -syntax

````
typedef struct _FSRTL_PER_FILEOBJECT_CONTEXT {
  LIST_ENTRY Links;
  PVOID      OwnerId;
  PVOID      InstanceId;
} FSRTL_PER_FILEOBJECT_CONTEXT, *PFSRTL_PER_FILEOBJECT_CONTEXT;
````


## -struct-fields

### -field Links

Link for this structure in the list of all per-file-object context structures associated with the same file object. <a href="ifsk.fsrtlinsertperfileobjectcontext">FsRtlInsertPerFileObjectContext</a> inserts this member into the list of all per-file-object context structures for the file object.


### -field OwnerId

A pointer to a filter-driver-allocated variable that uniquely identifies the owning filter of the per-file-object context structure. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the filter's device object or driver object. Note that the value of this member cannot be <b>NULL</b>.


### -field InstanceId

A pointer to a filter-driver-allocated variable that can be used to distinguish among per-file-object context structures created by the same filter driver. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the file object itself. Note that the value of this member can be <b>NULL</b>.


## -remarks
File system filter drivers can use the opaque FSRTL_PER_FILEOBJECT_CONTEXT structure to maintain context information for a file object. This structure can be used as-is or embedded in a driver-defined, per-file-object context structure.

Each file object can have one per-file-object context structure list associated with it. Each member of this list (that is, a particular per-file-object context structure) is owned by a filter driver. From the perspective of a filter driver, each filter driver can associate multiple per-file-object context structures for the same file object.

Each filter-defined per-file-object context structure must include an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure. The FSRTL_PER_FILEOBJECT_CONTEXT structure can be allocated from paged or nonpage pool and must be initialized using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a> macro.

To insert a FSRTL_PER_FILEOBJECT_CONTEXT structure or a filter-defined per-file-object context structure (containing an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure) into the list of all context structures for a file object, use the <a href="ifsk.fsrtlinsertperfileobjectcontext">FsRtlInsertPerFileObjectContext</a> function.

After a FSRTL_PER_FILEOBJECT_CONTEXT or per-file-object context structure has been associated with a file object, it can be retrieved by calling <a href="ifsk.fsrtllookupperfileobjectcontext">FsRtlLookupPerFileObjectContext </a>or removed by calling <a href="ifsk.fsrtlremoveperfileobjectcontext">FsRtlRemovePerFileObjectContext </a>(based upon the values of <b>OwnerId</b> and <b>InstanceId</b>).


<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>



<a href="ifsk.fsrtlinsertperfileobjectcontext">FsRtlInsertPerFileObjectContext</a>



<a href="ifsk.fsrtllookupperfileobjectcontext">FsRtlLookupPerFileObjectContext</a>



<a href="ifsk.fsrtlremoveperfileobjectcontext">FsRtlRemovePerFileObjectContext</a>

<p class="note">Instead, minifilters can use the following functions to associate context information with a file object:


<a href="ifsk.fltallocatecontext">FltAllocateContext</a>



<a href="ifsk.fltdeletecontext">FltDeleteContext</a>



<a href="ifsk.fltsetstreamhandlecontext">FltSetStreamHandleContext</a>



<a href="ifsk.fltdeletestreamhandlecontext">FltDeleteStreamHandleContext</a>



<a href="ifsk.fltgetstreamhandlecontext">FltGetStreamHandleContext</a>



<a href="ifsk.fltreleasecontext">FltReleaseContext</a>


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a> macro initializes a <b>FSRTL_PER_FILEOBJECT_CONTEXT</b> structure.

Parameters


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Fltkernel.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="kernel.driver_object">DRIVER_OBJECT</a>
</dt>
<dt>
<a href="kernel.file_object">FILE_OBJECT</a>
</dt>
<dt>
<a href="ifsk.fltallocatecontext">FltAllocateContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletecontext">FltDeleteContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletestreamhandlecontext">FltDeleteStreamHandleContext</a>
</dt>
<dt>
<a href="ifsk.fltgetstreamhandlecontext">FltGetStreamHandleContext</a>
</dt>
<dt>
<a href="ifsk.fltreleasecontext">FltReleaseContext</a>
</dt>
<dt>
<a href="ifsk.fltsetstreamhandlecontext">FltSetStreamHandleContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>
</dt>
<dt>
<a href="ifsk.fsrtlinsertperfileobjectcontext">FsRtlInsertPerFileObjectContext</a>
</dt>
<dt>
<a href="ifsk.fsrtllookupperfileobjectcontext">FsRtlLookupPerFileObjectContext</a>
</dt>
<dt>
<a href="ifsk.fsrtlremoveperfileobjectcontext">FsRtlRemovePerFileObjectContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_PER_FILEOBJECT_CONTEXT structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

