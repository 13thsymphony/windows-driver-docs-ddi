---
UID: NF:dbgeng.IDebugControl3.CloseLogFile
title: IDebugControl3::CloseLogFile method
author: windows-driver-content
description: The CloseLogFile method closes the currently-open log file.
old-location: debugger\closelogfile.htm
old-project: debugger
ms.assetid: 86ae188b-379c-474e-9f21-60286af19656
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CloseLogFile method [Windows Debugging], CloseLogFile method [Windows Debugging], IDebugControl interface, CloseLogFile method [Windows Debugging], IDebugControl2 interface, CloseLogFile method [Windows Debugging], IDebugControl3 interface, CloseLogFile,IDebugControl3.CloseLogFile, IDebugControl interface [Windows Debugging], CloseLogFile method, IDebugControl2 interface [Windows Debugging], CloseLogFile method, IDebugControl2::CloseLogFile, IDebugControl3, IDebugControl3 interface [Windows Debugging], CloseLogFile method, IDebugControl3::CloseLogFile, IDebugControl::CloseLogFile, IDebugControl_988fe3ac-a51d-4757-995d-40fe9d66aa02.xml, dbgeng/IDebugControl2::CloseLogFile, dbgeng/IDebugControl3::CloseLogFile, dbgeng/IDebugControl::CloseLogFile, debugger.closelogfile
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugControl.CloseLogFile
-	IDebugControl2.CloseLogFile
-	IDebugControl3.CloseLogFile
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# CloseLogFile method
The <b>CloseLogFile</b> method closes the currently-open log file.

## Syntax

````
HRESULT CloseLogFile();
````

## Parameters

This function has no parameters.

## Return Value

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
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

If no log file is open, this method has no effect.

For more about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547016">GetLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553154">OpenLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>



<a href="https://msdn.microsoft.com/730cfab3-5529-4054-ba62-8a780572603d">.logclose</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::CloseLogFile method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>