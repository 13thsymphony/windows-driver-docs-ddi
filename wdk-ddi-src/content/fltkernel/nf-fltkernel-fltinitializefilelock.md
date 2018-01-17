---
UID: NF:fltkernel.FltInitializeFileLock
title: FltInitializeFileLock function
author: windows-driver-content
description: The FltInitializeFileLock routine initializes an opaque FILE_LOCK structure that the caller has allocated from paged pool.
old-location: ifsk\fltinitializefilelock.htm
old-project: ifsk
ms.assetid: 84bfec05-9d77-433e-bec2-ad188269fc61
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltInitializeFileLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows XP with SP2 or Windows Server 2003 with SP1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltInitializeFileLock
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# FltInitializeFileLock function



## -description
The <b>FltInitializeFileLock</b> routine initializes an opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure that the caller has allocated from paged pool.



## -syntax

````
VOID FltInitializeFileLock(
  _Out_ PFILE_LOCK FileLock
);
````


## -parameters

### -param FileLock [out]

Pointer to an uninitialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure. 


## -returns
None


## -remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure is opaque: that is, its members are reserved for system use. 

Once initialized, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure can be used to lock a byte range in a file by calling <a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a>.

It is a programming error to call <b>FltInitializeFileLock</b> for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure that has already been initialized by <b>FltInitializeFileLock</b> or <a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a>, unless the structure has been uninitialized by a subsequent call to <a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>.

When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure is no longer needed, it can be uninitialized by calling <a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>. The uninitialized <b>FILE_LOCK</b> structure can then be initialized for reuse by calling <b>FltInitializeFileLock</b>.

To allocate and initialize a new opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure, call <a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a>. 

To free an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure, call <a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltchecklockforreadaccess.md">FltCheckLockForReadAccess</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltchecklockforwriteaccess.md">FltCheckLockForWriteAccess</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltInitializeFileLock routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

