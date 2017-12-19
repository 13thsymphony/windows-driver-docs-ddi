---
UID: NF.ntifs.FsRtlSetupAdvancedHeaderEx
title: FsRtlSetupAdvancedHeaderEx macro
author: windows-driver-content
description: The FsRtlSetupAdvancedHeaderEx macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with both stream and file contexts.
old-location: ifsk\fsrtlsetupadvancedheaderex.htm
old-project: ifsk
ms.assetid: 41e5d9f2-ac0b-4834-bca8-88ed872f2f70
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FsRtlSetupAdvancedHeaderEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Update Rollup for Microsoft Windows 2000 Service Pack 4 (SP4) and on Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlSetupAdvancedHeaderEx
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
req.irql: PASSIVE_LEVEL
---

# FsRtlSetupAdvancedHeaderEx macro



## -description
The <b>FsRtlSetupAdvancedHeaderEx</b> macro is used by file systems to initialize an <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with both stream and file contexts.



## -syntax

````
VOID FsRtlSetupAdvancedHeaderEx(
  _In_     PFSRTL_ADVANCED_FCB_HEADER AdvancedHeader,
  _In_opt_ PFAST_MUTEX                FastMutex,
  _In_opt_ PVOID                      *FileContextSupportPointer
);
````


## -parameters

### -param AdvancedHeader [in]

Pointer to the <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure to be initialized. 


### -param FastMutex [in, optional]

Pointer to an initialized fast mutex that will be used to synchronize access to certain FSRTL_ADVANCED_FCB_HEADER members (for more information, see <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>). The fast mutex must be allocated from nonpaged pool. This parameter is optional and can be <b>NULL</b>. Callers should set this parameter to <b>NULL</b> if they intend to use an already existing fast mutex object. If <i>FastMutex</i> is <b>NULL</b>, the caller must explicitly set the <b>FastMutex</b> member of the FSRTL_ADVANCED_FCB_HEADER structure, contained in the stream context object, to point to the existing fast mutex. (This can be done before or after calling <b>FsRtlSetupAdvancedHeaderEx</b>.)


### -param FileContextSupportPointer [in, optional]

A pointer to a pointer field used by the file system runtime library (FSRTL) package to track file contexts. 

This parameter is optional and can be <b>NULL</b>.  In particular:

<ul>
<li>
 For Microsoft Windows operating systems released prior to Windows Vista: Callers must set this parameter to <b>NULL</b>.

</li>
<li>
 For Windows operating systems starting with Windows Vista: If <i>FileContextSupportPointer</i> is not <b>NULL</b>, <i>FileContextSupportPointer</i> must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure.  To indicate that the file system driver does not support file contexts, callers must set <i>FileContextSupportPointer</i> to <b>NULL</b>.

</li>
</ul>

## -remarks
File systems use the <b>FsRtlSetupAdvancedHeaderEx</b> macro to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with stream and file contexts. 

When the advanced FCB header structure is no longer required, the file system must call <a href="ifsk.fsrtlteardownperstreamcontexts">FsRtlTeardownPerStreamContexts</a> to free all associated stream and file context structures.

For more information, see <a href="ifsk.tracking_per_stream_context_in_a_legacy_file_system_filter_driver">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available on Update Rollup for Microsoft Windows 2000 Service Pack 4 (SP4) and on Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>
</dt>
<dt>
<a href="ifsk.fsrtl_per_stream_context">FSRTL_PER_STREAM_CONTEXT</a>
</dt>
<dt>
<a href="ifsk.fsrtlgetperstreamcontextpointer">FsRtlGetPerStreamContextPointer</a>
</dt>
<dt>
<a href="ifsk.fsrtlinitperstreamcontext">FsRtlInitPerStreamContext</a>
</dt>
<dt>
<a href="ifsk.fsrtlinsertperstreamcontext">FsRtlInsertPerStreamContext</a>
</dt>
<dt>
<a href="ifsk.fsrtllookupperstreamcontext">FsRtlLookupPerStreamContext</a>
</dt>
<dt>
<a href="ifsk.fsrtlremoveperstreamcontext">FsRtlRemovePerStreamContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>
</dt>
<dt>
<a href="ifsk.fsrtlteardownperstreamcontexts">FsRtlTeardownPerStreamContexts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlSetupAdvancedHeaderEx function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

