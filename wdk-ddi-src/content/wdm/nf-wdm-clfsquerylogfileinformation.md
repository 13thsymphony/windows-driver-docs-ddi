---
UID : NF:wdm.ClfsQueryLogFileInformation
title : ClfsQueryLogFileInformation function
author : windows-driver-content
description : The ClfsQueryLogFileInformation routine returns metadata and state information for a specified CLFS stream or its underlying physical log or both.
old-location : kernel\clfsquerylogfileinformation.htm
old-project : kernel
ms.assetid : a907f219-9e4a-415f-821c-d419b7fde729
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : Clfs_ff89b511-dc33-4407-b967-170b82cb70c3.xml, wdm/ClfsQueryLogFileInformation, ClfsQueryLogFileInformation, kernel.clfsquerylogfileinformation, ClfsQueryLogFileInformation routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ClfsQueryLogFileInformation function
The <b>ClfsQueryLogFileInformation</b> routine returns metadata and state information for a specified CLFS stream or its underlying physical log or both.

## Syntax

````
NTSTATUS  ClfsQueryLogFileInformation(
  _In_    PLOG_FILE_OBJECT           plfoLog,
  _In_    CLFS_LOG_INFORMATION_CLASS eInformationClass,
  _Out_   PVOID                      pinfoBuffer,
  _Inout_ PULONG                     pcbBuffer
);
````

## Parameters

`plfoLog`

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.

`eInformationClass`

A value from the <a href="..\wdm\ne-wdm-_cls_log_information_class.md">CLFS_LOG_INFORMATION_CLASS</a> enumeration that specifies the type of information being requested.

`pinfoInputBuffer`

TBD

`cbinfoInputBuffer`

TBD

`pinfoBuffer`

A pointer to a buffer that receives the log information. The structure of this buffer depends on the value of <i>eInformationClass</i>. The following table shows the relationship between the information class and the data type of the buffer.
<table>
<tr>
<th>Value of <i>eInformationClass</i></th>
<th>Type of buffer pointed to by <i>pinfoBuffer</i></th>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_cls_information.md">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformationPhysical</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_cls_information.md">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogNameInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_clfs_log_name_information.md">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogPhysicalNameInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_clfs_log_name_information.md">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogStreamIdentifierInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_clfs_stream_id_information.md">CLFS_STREAM_ID_INFORMATION</a>


</td>
</tr>
</table>

`pcbInfoBuffer`

TBD


## Return Value

<b>ClfsQueryLogFileInformation</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## Remarks

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows. Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Clfs.lib |
| **DLL** | Clfs.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-clfssetlogfileinformation.md">ClfsSetLogFileInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsQueryLogFileInformation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>