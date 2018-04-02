---
UID: NF:wdm.ClfsGetContainerName
title: ClfsGetContainerName function
author: windows-driver-content
description: The ClfsGetContainerName routine returns the path name of a specified container.
old-location: kernel\clfsgetcontainername.htm
old-project: kernel
ms.assetid: 727b2e29-9e2d-4386-a30b-5727e1261fad
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsGetContainerName, ClfsGetContainerName routine [Kernel-Mode Driver Architecture], Clfs_dce31248-386b-4f6d-8e88-55ef9d70fe84.xml, kernel.clfsgetcontainername, wdm/ClfsGetContainerName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsGetContainerName
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ClfsGetContainerName function
The <b>ClfsGetContainerName</b> routine returns the path name of a specified container.

## Syntax

```
CLFSUSER_API NTSTATUS ClfsGetContainerName(
  PLOG_FILE_OBJECT  plfoLog,
  CLFS_CONTAINER_ID cidLogicalContainer,
  PUNICODE_STRING   puszContainerName,
  PULONG            pcActualLenContainerName
);
```

## Parameters

`plfoLog`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents a CLFS log. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.

`cidLogicalContainer`

The logical identifier of a container in the CLFS log.

`puszContainerName`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure. The <b>Buffer</b> member of <i>puszContainerName</i> must point to a caller-allocated buffer that receives the path name of the container. The <b>MaximumLength</b> member must supply the size of the buffer.

`pcActualLenContainerName`

A pointer to a ULONG-typed variable that receives the actual length, in Unicode characters, of the container's path name. This parameter can be <b>NULL</b>.


## Return Value

<b>ClfsGetContainerName</b> returns one of the status codes defined in Ntstatus.h. The following table gives the meanings of various return values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The actual length, in Unicode characters, of the full path name is larger than <i>puszContainerName</i>-&gt;<b>MaximumLength</b>. The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container truncated to the number of characters specified by <i>puszContainerName</i>-&gt;<b>MaximumLength</b>. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other</b></dt>
</dl>
</td>
<td width="60%">
On return, the contents of <i>puszContainerName</i>-&gt;<b>Buffer</b> and <i>pcActualLenContainerName</i> are undefined.

</td>
</tr>
</table>

## Remarks

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | Clfs.lib |
| **DLL** | Clfs.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540768">ClfsAddLogContainer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541715">ClfsRemoveLogContainer</a>