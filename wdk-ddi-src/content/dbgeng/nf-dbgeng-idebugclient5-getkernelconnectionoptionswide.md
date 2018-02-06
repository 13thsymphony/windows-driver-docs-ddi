---
UID: NF:dbgeng.IDebugClient5.GetKernelConnectionOptionsWide
title: IDebugClient5::GetKernelConnectionOptionsWide method
author: windows-driver-content
description: The GetKernelConnectionOptionsWide method returns the connection options for the current kernel target.
old-location: debugger\getkernelconnectionoptionswide.htm
old-project: debugger
ms.assetid: f85ef2cf-704a-4a7c-aeeb-483a7b1fdc8f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.getkernelconnectionoptionswide, GetKernelConnectionOptionsWide method [Windows Debugging], IDebugClient5 interface, IDebugClient5, dbgeng/IDebugClient5::GetKernelConnectionOptionsWide, GetKernelConnectionOptionsWide, IDebugClient5::GetKernelConnectionOptionsWide, GetKernelConnectionOptionsWide method [Windows Debugging], IDebugClient5 interface [Windows Debugging], GetKernelConnectionOptionsWide method
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
-	IDebugClient5.GetKernelConnectionOptionsWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetKernelConnectionOptionsWide method
The <b>GetKernelConnectionOptionsWide</b> method returns the connection options for the current kernel target.

## Syntax

````
HRESULT GetKernelConnectionOptionsWide(
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG OptionsSize
);
````

## Parameters

`Buffer`

Specifies the buffer to receive the connection options.

`BufferSize`

Specifies the size in characters of the buffer <i>Buffer</i>.

`OptionsSize`

Receives the size in characters of the connection options.  If <i>OptionsSize</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The size of the string was greater than the size of the buffer, so it was truncated to fit into the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The current target is not a standard live kernel target.

</td>
</tr>
</table>

## Remarks

This method is available only for live kernel targets that are not local and not connected through eXDI.

The connection options returned are the same options used to connect to the kernel.

For more information about connecting to live kernel-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552005">Live Kernel-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538145">AttachKernel</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetKernelConnectionOptionsWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>