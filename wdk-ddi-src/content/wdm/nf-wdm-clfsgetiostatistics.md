---
UID : NF:wdm.ClfsGetIoStatistics
title : ClfsGetIoStatistics function
author : windows-driver-content
description : The ClfsGetIoStatistics routine returns I/O statistics for a specified CLFS log.
old-location : kernel\clfsgetiostatistics.htm
old-project : kernel
ms.assetid : 68c04751-761c-4e32-927d-aad61813cd38
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ClfsGetIoStatistics
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ClfsGetIoStatistics
req.alt-loc : Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Clfs.lib
req.dll : Clfs.sys
req.irql : <= APC_LEVEL
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ClfsGetIoStatistics function
The <b>ClfsGetIoStatistics</b> routine returns I/O statistics for a specified CLFS log.

## Syntax

````
NTSTATUS ClfsGetIoStatistics(
  _In_      PLOG_FILE_OBJECT   plfoLog,
  _Inout_   PVOID              pvStatsBuffer,
  _In_      ULONG              cbStatsBuffer,
  _In_      CLFS_IOSTATS_CLASS eStatsClass,
  _Out_opt_ PULONG             pcbStatsWritten
);
````

## Parameters

`plfoLog`

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The I/O statistics will be collected for the stream's underlying log on stable storage. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.

`pvStatsBuffer`

A pointer to a <a href="..\wdm\ns-wdm-_cls_io_statistics.md">CLFS_IO_STATISTICS</a> structure that receives the I/O statistics data.

`cbStatsBuffer`

The size, in bytes, of the buffer pointed to by <i>pvStatsBuffer</i>. This parameter must be at least <b>sizeof</b>(<a href="..\wdm\ns-wdm-_cls_io_statistics_header.md">CLFS_IO_STATISTICS_HEADER</a>). If this parameter is less than <b>sizeof</b>(<b>CLFS_IO_STATISTICS</b>), <i>pvStatsBuffer</i> will receive only a portion of the available I/O statistics.

`eStatsClass`

This parameter is reserved for future use.

`pcbStatsWritten`

A pointer to a ULONG-typed variable that receives the number of bytes actually written to <i>pvStatsBuffer</i>. This parameter can be <b>NULL</b>.


## Return Value

<b>ClfsGetIoStatistics</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## Remarks

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsGetIoStatistics routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>