---
UID: NF.dbgeng.IDebugControl3.ExecuteCommandFile
title: IDebugControl3::ExecuteCommandFile
author: windows-driver-content
description: The ExecuteCommandFile method opens the specified file and executes the debugger commands that are contained within.
old-location: debugger\executecommandfile.htm
ms.assetid: 6b8f53d7-361c-40a3-b93c-39e653bd9032
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl.ExecuteCommandFile,IDebugControl2.ExecuteCommandFile,IDebugControl3.ExecuteCommandFile
req.alt-loc: dbgeng.h
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
ms.keywords: IDebugControl3, ExecuteCommandFile, IDebugControl3::ExecuteCommandFile
req.iface: IDebugControl3
---

# IDebugControl3::ExecuteCommandFile method



## -description
<p>The <b>ExecuteCommandFile</b>  method opens the specified file and executes the debugger commands that are contained within.</p>


## -syntax

````
HRESULT ExecuteCommandFile(
  [in] ULONG OutputControl,
  [in] PCSTR CommandFile,
  [in] ULONG Flags
);
````


## -parameters
<dl>

### -param <i>OutputControl</i> [in]

<dd>
<p>Specifies where to send the output of the command.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.</p>
</dd>

### -param <i>CommandFile</i> [in]

<dd>
<p>Specifies the name of the file that contains the commands to execute.  This file is opened for reading and its contents are interpreted as if they had been typed into the debugger console.</p>
</dd>

### -param <i>Flags</i> [in]

<dd>
<p>Specifies execution options for the command.  The default options are to log the command but not to send it to the output.  For details about the values that <i>Flags</i> can take, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>.</p>
</dd>
</dl>

## -returns
<p>This method might also return error values, including error values caused by a failure to open the specified file.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>This method reads the specified file and execute the commands one line at a time using <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>.  If an exception occurred while executing a line, the execution will continue with the next line.</p>

<p>This method reads the specified file and execute the commands one line at a time using <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>.  If an exception occurred while executing a line, the execution will continue with the next line.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::ExecuteCommandFile method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
