---
UID: NF:dbgeng.IDebugControl2.GetLogFile
title: IDebugControl2::GetLogFile method
author: windows-driver-content
description: The GetLogFile method returns the name of the currently open log file.
old-location: debugger\getlogfile.htm
old-project: debugger
ms.assetid: 9d71a817-55b5-4042-8de8-15b23e51dffd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetLogFile method [Windows Debugging], GetLogFile method [Windows Debugging], IDebugControl interface, GetLogFile method [Windows Debugging], IDebugControl2 interface, GetLogFile method [Windows Debugging], IDebugControl3 interface, GetLogFile,IDebugControl2.GetLogFile, IDebugControl interface [Windows Debugging], GetLogFile method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetLogFile method, IDebugControl2::GetLogFile, IDebugControl3 interface [Windows Debugging], GetLogFile method, IDebugControl3::GetLogFile, IDebugControl::GetLogFile, IDebugControl_cad2fa56-b2ca-4a26-822e-193acf602913.xml, dbgeng/IDebugControl2::GetLogFile, dbgeng/IDebugControl3::GetLogFile, dbgeng/IDebugControl::GetLogFile, debugger.getlogfile
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
-	IDebugControl.GetLogFile
-	IDebugControl2.GetLogFile
-	IDebugControl3.GetLogFile
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetLogFile method
The <b>GetLogFile</b>  method returns the name of the currently open log file.

## Syntax

````
HRESULT GetLogFile(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG FileSize,
  [out]           PBOOL  Append
);
````

## Parameters

`Buffer`

Receives the name of the currently open log file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size, in characters, of the <i>Buffer</i> buffer.

`FileSize`

Receives the size, in characters, of the name of the log file.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.

`Append`

Receives <b>TRUE</b> if log messages are appended to the log file, or <b>FALSE</b> if the contents of the log file were discarded when the file was opened.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the name of the log file was too long to fit in the <i>Buffer</i> buffer so the name was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
There is no currently open log file.

</td>
</tr>
</table>

## Remarks

<b>GetLogFile</b> and <b>GetLogFileWide</b> behave the same way as <a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a> and <b>GetLogFile2Wide</b> with <i>Append</i> receiving only the information about the DEBUG_LOG_APPEND flag.

For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553154">OpenLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539148">CloseLogFile</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>