---
UID: NF:dbgeng.IDebugControl4.OpenLogFile2Wide
title: IDebugControl4::OpenLogFile2Wide method
author: windows-driver-content
description: The OpenLogFile2Wide method opens a log file that will receive output from the client objects.
old-location: debugger\openlogfile2wide.htm
old-project: debugger
ms.assetid: 28d23e5e-4daf-4176-8d7b-af92eee8ccef
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: OpenLogFile2Wide method [Windows Debugging], IDebugControl4 interface, IDebugControl4 interface [Windows Debugging], OpenLogFile2Wide method, OpenLogFile2Wide, dbgeng/IDebugControl4::OpenLogFile2Wide, IDebugControl4::OpenLogFile2Wide, IDebugControl4, debugger.openlogfile2wide, OpenLogFile2Wide method [Windows Debugging]
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl4.OpenLogFile2Wide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# OpenLogFile2Wide method
The <b>OpenLogFile2Wide</b>  method opens a log file that will receive output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">client objects</a>.

## Syntax

````
HRESULT OpenLogFile2Wide(
  [in] PCWSTR File,
  [in] ULONG  Flags
);
````

## Parameters

`File`

Specifies the name of the log file.  <i>File</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger  was started.  If the file does not exist, it will be created.

`Flags`

Specifies the bit-flags that control the nature of the log file.  <i>Flags</i> can contain flags from the following table.

<table>
<tr>
<th>Flag</th>
<th>Effect when set</th>
</tr>
<tr>
<td>
DEBUG_LOG_APPEND

</td>
<td>
Output will be appended to the log file instead of discarding the contents of the log file.

</td>
</tr>
<tr>
<td>
DEBUG_LOG_UNICODE

</td>
<td>
The format of the log file will be Unicode instead of ASCII.

</td>
</tr>
</table>
 

Alternatively, <i>Flags</i> can be set to DEBUG_LOG_DEFAULT for the default set of options that contains none of the flags.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

Only one log file can be open at a time.  If there is already a log file open, it will be closed.

For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553154">OpenLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556734">SetLogMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539148">CloseLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564018">.logopen (Open Log File)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563986">.logappend (Append Log File)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::OpenLogFile2Wide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>