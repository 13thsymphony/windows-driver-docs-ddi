---
UID : NF:wdm.ClfsReadNextLogRecord
title : ClfsReadNextLogRecord function
author : windows-driver-content
description : The ClfsReadNextLogRecord routine reads the next record in a sequence, relative to the current record in a read context.
old-location : kernel\clfsreadnextlogrecord.htm
old-project : kernel
ms.assetid : 4990f3d7-e48c-49ee-9384-4bcad93c9281
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.clfsreadnextlogrecord, Clfs_4e00ce69-12c3-48c1-ba3b-1c85158afc12.xml, ClfsReadNextLogRecord, ClfsReadNextLogRecord routine [Kernel-Mode Driver Architecture], wdm/ClfsReadNextLogRecord
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ClfsReadNextLogRecord function
The <b>ClfsReadNextLogRecord</b> routine reads the next record in a sequence, relative to the current record in a read context.

## Syntax

````
NTSTATUS ClfsReadNextLogRecord(
  _Inout_  PVOID             pvReadContext,
  _Out_    PVOID             *ppvBuffer,
  _Out_    PULONG            pcbBuffer,
  _Inout_  PCLFS_RECORD_TYPE peRecordType,
  _In_opt_ PCLFS_LSN         plsnUser,
  _Out_    PCLFS_LSN         plsnUndoNext,
  _Out_    PCLFS_LSN         plsnPrevious,
  _Out_    PCLFS_LSN         plsnRecord
);
````

## Parameters

`pvReadContext`

A pointer to a read context that the caller previously obtained by calling <a href="..\wdm\nf-wdm-clfsreadlogrecord.md">ClfsReadLogRecord</a> or <a href="..\wdm\nf-wdm-clfsreadrestartarea.md">ClfsReadRestartArea</a>.

`ppvBuffer`

A pointer to a variable that receives a pointer to a buffer that contains the record data.

`pcbBuffer`

A pointer to a ULONG-typed variable that receives the size, in bytes, of the buffer pointed to by *<i>ppvBuffer</i>. This is the length of the data buffer of the record read.

`peRecordType`

A pointer to a variable of type CLFS_RECORD_TYPE. The caller must set this parameter to one of the following values.
<table>
<tr>
<th>Value</th>
<th>Record that will be read</th>
</tr>
<tr>
<td>
<b>ClfsDataRecord</b>

</td>
<td>
The next data record.

</td>
</tr>
<tr>
<td>
<b>ClfsRestartRecord</b>

</td>
<td>
The next restart record.

</td>
</tr>
<tr>
<td>
<b>ClfsClientRecord</b>

</td>
<td>
The next record that is either a data record or a restart record.

</td>
</tr>
</table>

`plsnUser`

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that supplies the LSN of the record to be read. The specified record is read instead of the record that would have been read according to the mode (<b>ClfsContextUndoNext</b>, <b>ClfsContextPrevious</b>, or <b>ClfsContextForward</b>) of the read context (<i>pvReadContext</i>). The LSN supplied in <i>plsnUser</i> must be less than the current LSN of the read context. This parameter can be <b>NULL</b>.

`plsnUndoNext`

A pointer to a <b>CLFS_LSN</b> structure that receives the undo-next LSN of the record that is read.

`plsnPrevious`

A pointer to a <b>CLFS_LSN</b> structure that receives the previous LSN of the record that was read.

`plsnRecord`

A pointer to a <b>CLFS_LSN</b> structure that receives the LSN of the record that was read.


## Return Value

<b>ClfsReadNextLogRecord</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## Remarks

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 

For information about reading records from CLFS streams, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560785">Reading Data Records from a CLFS Stream</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560786">Reading Restart Records from a CLFS Stream</a>.

Read contexts are not thread-safe. Clients are responsible for serializing access to read contexts.

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

<a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a>

<a href="..\wdm\nf-wdm-clfsreadlogrecord.md">ClfsReadLogRecord</a>

<a href="..\wdm\nf-wdm-clfsreadrestartarea.md">ClfsReadRestartArea</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsReadNextLogRecord routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>