---
UID: NF.ntifs.FsRtlRemovePerFileObjectContext
title: FsRtlRemovePerFileObjectContext function
author: windows-driver-content
description: For a &#0034;legacy&#0034; file system filter driver, the FsRtlRemovePerFileObjectContext function unlinks a per-file-object context information structure from the list of per-file-object contexts previously associated with a file object.
old-location: ifsk\fsrtlremoveperfileobjectcontext.htm
old-project: ifsk
ms.assetid: 84d359db-08d7-4f42-b912-02f3d483aa05
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlRemovePerFileObjectContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlRemovePerFileObjectContext
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
---

# FsRtlRemovePerFileObjectContext function



## -description
For a "legacy" file system filter driver, the <b>FsRtlRemovePerFileObjectContext</b> function unlinks a per-file-object context information structure from the list of per-file-object contexts previously associated with a file object.



## -syntax

````
PFSRTL_PER_FILEOBJECT_CONTEXT FsRtlRemovePerFileObjectContext(
  _In_     PFILE_OBJECT FileObject,
  _In_opt_ PVOID        OwnerId,
  _In_opt_ PVOID        InstanceId
);
````


## -parameters

### -param FileObject [in]

A pointer to a file object for which to remove context information.


### -param OwnerId [in, optional]

A pointer to a caller-allocated variable that uniquely identifies the owning filter of the per-file-object context structure. The format of this variable is filter-driver-specific.


### -param InstanceId [in, optional]

A pointer to a caller-allocated variable that can be used to distinguish among per-file-object context structures created by the same filter driver. The format of this variable is filter-driver-specific. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>FsRtlRemovePerFileObjectContext</b> unlinks and returns a pointer to the first matching per-file-object context that is found. If no match is found, <b>FsRtlRemovePerFileObjectContext</b> returns <b>NULL</b>.


## -remarks
A "legacy" file system filter driver calls <b>FsRtlRemovePerFileObjectContext </b>to unlink its own per-file-object context structure from the list of per-file-object contexts associated with the file object. All such context structures must have previously been associated with the file object by calling <a href="ifsk.fsrtlinsertperfileobjectcontext">FsRtlInsertPerFileObjectContext</a>.

If the call to <b>FsRtlRemovePerFileObjectContext </b>is successful, the first per-file-object context structure matching <i>OwnerId</i> (and <i>InstanceId</i>, if present) is unlinked and a pointer to it returned. This pointer can be used by the filter driver to free the unlinked context structure.

To initialize a per-file-object context structure, use the <a href="https://msdn.microsoft.com/8ed219c8-927e-47b1-8ebf-689535dea0fc">FsRtlInitPerFileObjectContext </a>macro.

To associate an initialized per-file-object context structure with a file object, use the <a href="ifsk.fsrtlinsertperfileobjectcontext">FsRtlInsertPerFileObjectContext</a> function.

To retrieve a per-file-object context structure that is associated with a file object, use the <a href="ifsk.fsrtllookupperfileobjectcontext">FsRtlLookupPerFileObjectContext</a> function.

Additionally, file system minifilter drivers must not use the <b>FsRtl</b><i>Xxx</i><b>PerFileObjectContext</b> functions. Instead, they can use the appropriate <b>Flt</b><i>Xxx</i><b>Context</b> functions. For additional information, see the <a href="ifsk.fsrtl_per_fileobject_context">FSRTL_PER_FILEOBJECT_CONTEXT</a> topic.


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
<a href="ifsk.fsrtl_per_fileobject_context">FSRTL_PER_FILEOBJECT_CONTEXT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>
</dt>
<dt>
<a href="ifsk.fsrtllookupperfileobjectcontext">FsRtlLookupPerFileObjectContext</a>
</dt>
<dt>
<a href="ifsk.fsrtlinsertperfileobjectcontext">FsRtlInsertPerFileObjectContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlRemovePerFileObjectContext function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

