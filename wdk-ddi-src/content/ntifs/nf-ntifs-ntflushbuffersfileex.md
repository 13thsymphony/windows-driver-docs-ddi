---
UID : NF:ntifs.NtFlushBuffersFileEx
title : NtFlushBuffersFileEx function
author : windows-driver-content
description : The ZwFlushBuffersFileEx routine is called by a file system filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.
old-location : kernel\zwflushbuffersfileex.htm
old-project : kernel
ms.assetid : C081CCF5-D13C-405C-A430-31805A16724A
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : NtFlushBuffersFileEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ZwFlushBuffersFileEx,NtFlushBuffersFileEx
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL (See Remarks section.)
req.typenames : TOKEN_TYPE
---


# NtFlushBuffersFileEx function
The <b>ZwFlushBuffersFileEx</b> routine is called by a file system filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.

## Syntax

````
NTSTATUS ZwFlushBuffersFileEx(
  _In_  HANDLE           FileHandle,
  _In_  ULONG            Flags,
  _Out_ PIO_STATUS_BLOCK IoStatusBlock
);
````

## Parameters

`FileHandle`

Handle returned by <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> or <a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a> for the file whose buffers will be flushed. This parameter is required and cannot be <b>NULL</b>.

`Flags`

Flush operation flags. <i>Flags</i> can be 0 or one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

`Parameters`



`ParametersSize`



`IoStatusBlock`

Address of the caller's I/O status block. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>ZwFlushBuffersFileEx</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 
<dl>
<dt><b>STATUS_MEDIA_WRITE_PROTECTED</b></dt>
</dl>The file resides on a write-protected volume; this is an error code.
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>The file resides on a volume that is not currently mounted; this is an error code.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The file does has neither write or append access.

## Remarks

A file system filter driver can call <b>ZwFlushBuffersFileEx</b> to issue an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a> request to the file system for a given file. The flush operation is synchronous. 

Minifilter drivers should call <a href="..\fltkernel\nf-fltkernel-fltflushbuffers.md">FltFlushBuffers</a> instead of calling <b>ZwFlushBuffersFileEx</b>. 

Callers of <b>ZwFlushBuffersFileEx</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (See Remarks section.) |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltflushbuffers.md">FltFlushBuffers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwFlushBuffersFileEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>