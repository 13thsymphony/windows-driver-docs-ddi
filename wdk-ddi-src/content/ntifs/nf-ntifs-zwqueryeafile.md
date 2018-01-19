---
UID : NF:ntifs.ZwQueryEaFile
title : ZwQueryEaFile function
author : windows-driver-content
description : The ZwQueryEaFile routine returns information about extended-attribute (EA) values for a file.
old-location : kernel\zwqueryeafile.htm
old-project : kernel
ms.assetid : c4261a83-3c91-4bc1-93bf-d2d04c324e94
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ZwQueryEaFile
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : FltKernel.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows 2000 and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ZwQueryEaFile
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
req.typenames : TOKEN_TYPE
---


# ZwQueryEaFile function
The <b>ZwQueryEaFile</b> routine returns 
    information about extended-attribute (EA) values for a file.

## Syntax

````
NTSTATUS ZwQueryEaFile(
  _In_     HANDLE           FileHandle,
  _Out_    PIO_STATUS_BLOCK IoStatusBlock,
  _Out_    PVOID            Buffer,
  _In_     ULONG            Length,
  _In_     BOOLEAN          ReturnSingleEntry,
  _In_opt_ PVOID            EaList,
  _In_     ULONG            EaListLength,
  _In_opt_ PULONG           EaIndex,
  _In_     BOOLEAN          RestartScan
);
````

## Parameters

`FileHandle`

The handle for the file on which the operation is to be performed.

`IoStatusBlock`

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that 
      receives the final completion status and other information about the requested operation.

`Buffer`

A pointer to a caller-supplied 
      <a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>-structured output 
      buffer, where the extended attribute values are to be returned.

`Length`

The length, in bytes, of the buffer that the <i>Buffer</i> parameter points to.

`ReturnSingleEntry`

Set to <b>TRUE</b> if 
      <b>ZwQueryEaFile</b> should return only the first entry that 
      is found.

`EaList`

A pointer to a caller-supplied 
      <a href="..\ntifs\ns-ntifs-_file_get_ea_information.md">FILE_GET_EA_INFORMATION</a>-structured input 
      buffer, which specifies the extended attributes to be queried. This parameter is optional and can be 
      <b>NULL</b>.

`EaListLength`

The length, in bytes, of the buffer that the <i>EaList</i> parameter points to.

`EaIndex`

The index of the entry at which scanning the file's extended-attribute list should begin. This parameter is 
      ignored if the <i>EaList</i> parameter points to a nonempty list. This parameter is optional 
      and can be <b>NULL</b>.

`RestartScan`

Set to <b>TRUE</b> if 
      <b>ZwQueryEaFile</b> should begin the scan at the first 
      entry in the file's extended-attribute list. If this parameter is set to <b>FALSE</b>, the 
      routine resumes the scan from a previous call to 
      <b>ZwQueryEaFile</b>.


## Return Value

<b>ZwQueryEaFile</b> returns 
      <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value such as 
      the following:
<dl>
<dt>STATUS_EAS_NOT_SUPPORTED</dt>
</dl>The file system does not support extended attributes. This is an error code.
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>The <a href="..\ntifs\nf-ntifs-zwqueryeafile.md">ZwQueryEaFile</a> routine encountered a pool 
        allocation failure. This is an error code.
<dl>
<dt>STATUS_EA_LIST_INCONSISTENT</dt>
</dl>The <i>EaList</i> parameter is not formatted correctly. This is an error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<dl>
<dt>
<a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_file_get_ea_information.md">FILE_GET_EA_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwseteafile.md">ZwSetEaFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryEaFile routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>