---
UID : NF:fltkernel.FltCheckLockForReadAccess
title : FltCheckLockForReadAccess function
author : windows-driver-content
description : The FltCheckLockForReadAccess routine determines whether the caller has read access to a locked byte range of a file.
old-location : ifsk\fltchecklockforreadaccess.htm
old-project : ifsk
ms.assetid : 18920aaa-ae43-48ec-a06d-69ccaf75ebd8
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltCheckLockForReadAccess
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FltCheckLockForReadAccess
req.alt-loc : FltMgr.lib,FltMgr.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : FltMgr.lib
req.dll : 
req.irql : <= APC_LEVEL
req.typenames : EXpsFontRestriction
---


# FltCheckLockForReadAccess function
The <b>FltCheckLockForReadAccess</b> routine determines whether the caller has read access to a locked byte range of a file.

## Syntax

````
BOOLEAN FltCheckLockForReadAccess(
  _In_ PFILE_LOCK         FileLock,
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````

## Parameters

`FileLock`

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a> or <a href="..\fltkernel\nf-fltkernel-fltinitializefilelock.md">FltInitializeFileLock</a>.

`CallbackData`

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> operation.


## Return Value

<b>FltCheckLockForReadAccess</b> returns <b>TRUE</b> if the process has read access, <b>FALSE</b> otherwise.

## Remarks

This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

<b>FltCheckLockForReadAccess</b> checks whether the caller has read access to the entire byte range indicated in the callback data structure. 

<b>FltCheckLockForReadAccess</b> does not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> operation. 

To allocate and initialize a new file lock structure, call <a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a>. 

To free an initialized FILE_LOCK structure, call <a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltchecklockforwriteaccess.md">FltCheckLockForWriteAccess</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltinitializefilelock.md">FltInitializeFileLock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess~r1.md">FsRtlCheckLockForReadAccess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCheckLockForReadAccess routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>