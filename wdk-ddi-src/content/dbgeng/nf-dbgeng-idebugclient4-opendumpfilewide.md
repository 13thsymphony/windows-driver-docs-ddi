---
UID: NF:dbgeng.IDebugClient4.OpenDumpFileWide
title: IDebugClient4::OpenDumpFileWide method
author: windows-driver-content
description: The OpenDumpFileWide method opens a dump file as a debugger target.
old-location: debugger\opendumpfilewide.htm
old-project: debugger
ms.assetid: 56efc94f-ef1e-41f9-ab99-57f0be34a770
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient4, IDebugClient4 interface [Windows Debugging], OpenDumpFileWide method, IDebugClient4::OpenDumpFileWide, IDebugClient5 interface [Windows Debugging], OpenDumpFileWide method, IDebugClient5::OpenDumpFileWide, IDebugClient_e3280682-6272-4324-bba5-120a95f27b15.xml, OpenDumpFileWide method [Windows Debugging], OpenDumpFileWide method [Windows Debugging], IDebugClient4 interface, OpenDumpFileWide method [Windows Debugging], IDebugClient5 interface, OpenDumpFileWide,IDebugClient4.OpenDumpFileWide, dbgeng/IDebugClient4::OpenDumpFileWide, dbgeng/IDebugClient5::OpenDumpFileWide, debugger.opendumpfilewide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient4.OpenDumpFileWide
-	IDebugClient5.OpenDumpFileWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# OpenDumpFileWide method
The <b>OpenDumpFileWide</b> method opens a dump file as a debugger target.

## Syntax

````
HRESULT OpenDumpFileWide(
  [in, optional] PCWSTR  FileName,
  [in]           ULONG64 FileHandle
);
````

## Parameters

`FileName`

Specifies the name of the dump file to open -- unless <i>FileHandle</i> is not zero, in which case <i>FileName</i> is used only when the engine is queried for the name of the dump file.  <i>FileName</i> must include the file name extension.  <i>FileName</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.  <i>FileName</i> can also be in the form of a file URL, starting with "file://".  If <i>FileName</i> specifies a cabinet (.cab) file, the cabinet file is searched for the first file with extension .kdmp, then .hdmp, then .mdmp, and finally .dmp.

`FileHandle`

Specifies the file handle of the dump file to open.  If <i>FileHandle</i> is zero, <i>FileName</i> is used to open the dump file.  Otherwise, if <i>FileName</i> is not <b>NULL</b>, the engine returns it when queried for the name of the dump file.  If <i>FileHandle</i> is not zero and <i>FileName</i> is <b>NULL</b>, the engine will return <b>&lt;HandleOnly&gt;</b> for the file name.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>

## Remarks

The ASCII version of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>.

<div class="alert"><b>Note</b>    The engine doesn't completely attach to the dump file until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> method has been called.  When a dump file is created from a process or kernel, information about the last event is stored in the dump file.  After the dump file is opened, the next time execution is attempted, the engine will generate this event for the event callbacks.  Only then does the dump file become available in the debugging session.</div>
<div> </div>
For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564611">.opendump (Open Dump File)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>