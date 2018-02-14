---
UID: NF:ntifs.FsRtlQueryKernelEaFile
title: FsRtlQueryKernelEaFile function
author: windows-driver-content
description: The routine FsRtlQueryKernelEaFile is used to build an explicit QueryEA request and synchronously wait for it to complete, returning the result. This allows the caller to do this by FileObject instead of a handle.
old-location: ifsk\fsrtlquerykerneleafile.htm
old-project: ifsk
ms.assetid: B57BC3A4-6116-48EA-905A-CFA7AC0A5E8F
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FsRtlQueryKernelEaFile, ifsk.fsrtlquerykerneleafile, ntifs/FsRtlQueryKernelEaFile, FsRtlQueryKernelEaFile routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FsRtlQueryKernelEaFile
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlQueryKernelEaFile function
The routine <b>FsRtlQueryKernelEaFile</b> is used to build an explicit QueryEA request and synchronously wait
    for it to complete, returning the result. This allows the caller to do
    this by FileObject instead of a handle.

## Syntax

````
NTSTATUS FsRtlQueryKernelEaFile(
  _In_      PFILE_OBJECT                              FileObject,
  _Out_     bcount_part(Length,*LengthReturned) PVOID ReturnedEaData,
  _In_      ULONG                                     Length,
  _In_      BOOLEAN                                   ReturnSingleEntry,
  _In_      bcount_opt(EaListLength) PVOID            EaList,
  _In_      ULONG                                     EaListLength,
  _In_opt_  PULONG                                    EaIndex,
  _In_      BOOLEAN                                   RestartScan,
  _Out_opt_ PULONG                                    LengthReturned
);
````

## Parameters

`FileObject`

A pointer to a <b>FileObject</b> to send the QueryEA request to.

`ReturnedEaData`

A pointer to a caller-supplied <a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>-structured output buffer, where the extended attribute values are to be returned.

`Length`

Specifies the length, in bytes, of <b>ReturnedEaData</b>

`ReturnSingleEntry`

Specifies whether only a single entry should be returned
        rather than filling the buffer with as many EAs as possible.

`EaList`

A pointer to a caller-supplied <a href="..\ntifs\ns-ntifs-_file_get_ea_information.md">FILE_GET_EA_INFORMATION</a>-structured input buffer, which specifies the extended attributes to be queried. This parameter is optional and can be<b> NULL</b>.

`EaListLength`

Specifies the length of <b>EaList</b>, if an EA list was
        supplied.

`EaIndex`

Supplies the optional index of an EA whose value is to be
        returned.  If specified, then only that EA is returned.

`RestartScan`

Specifies whether the scan of the EAs should be restarted
        from the beginning.

`LengthReturned`

Specifies the amount of valid data that is returned in the
        <b>ReturnedEaData</b> buffer.


## Return Value

The routine <b>FsRtlQueryKernelEaFile</b> returns one of the status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EAS_NOT_SUPPORTED </b></dt>
</dl>
</td>
<td width="60%">
The file system does not support extended attributes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request failed as it was a direct device open.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The  I/O request packet (IRP) could not be allocated for this request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful.

</td>
</tr>
</table>

## Remarks

This routine <b>FsRtlQueryKernelEaFile </b>assumes all passed in buffers are from kernel mode as it  requires that the given Input and Output buffers if specified, be kernel mode addresses.  The operation will fail if a user mode address is specified.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | ntifs.h |
| **Library** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff961908">ZwSetEaFile</a>



<a href="https://msdn.microsoft.com/E5EA2E40-2CC3-4C7B-8BCC-4793F76ECBAD">FsRtlSetKernelEaFile</a>



<a href="..\ntifs\nf-ntifs-zwqueryeafile.md">ZwQueryEaFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlQueryKernelEaFile routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>