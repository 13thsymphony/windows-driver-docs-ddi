---
UID: NF:dbgeng.IDebugClient3.GetKernelConnectionOptions
title: IDebugClient3::GetKernelConnectionOptions method
author: windows-driver-content
description: The GetKernelConnectionOptions method returns the connection options for the current kernel target.
old-location: debugger\getkernelconnectionoptions.htm
old-project: debugger
ms.assetid: 2862fe26-1613-4fc2-98e1-3deb5078d1e2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetKernelConnectionOptions method [Windows Debugging], GetKernelConnectionOptions method [Windows Debugging], IDebugClient interface, GetKernelConnectionOptions method [Windows Debugging], IDebugClient2 interface, GetKernelConnectionOptions method [Windows Debugging], IDebugClient3 interface, GetKernelConnectionOptions method [Windows Debugging], IDebugClient4 interface, GetKernelConnectionOptions method [Windows Debugging], IDebugClient5 interface, GetKernelConnectionOptions,IDebugClient3.GetKernelConnectionOptions, IDebugClient interface [Windows Debugging], GetKernelConnectionOptions method, IDebugClient2 interface [Windows Debugging], GetKernelConnectionOptions method, IDebugClient2::GetKernelConnectionOptions, IDebugClient3, IDebugClient3 interface [Windows Debugging], GetKernelConnectionOptions method, IDebugClient3::GetKernelConnectionOptions, IDebugClient4 interface [Windows Debugging], GetKernelConnectionOptions method, IDebugClient4::GetKernelConnectionOptions, IDebugClient5 interface [Windows Debugging], GetKernelConnectionOptions method, IDebugClient5::GetKernelConnectionOptions, IDebugClient::GetKernelConnectionOptions, IDebugClient_5a7fe06a-42e4-4bdd-935c-8130cdfef568.xml, dbgeng/IDebugClient2::GetKernelConnectionOptions, dbgeng/IDebugClient3::GetKernelConnectionOptions, dbgeng/IDebugClient4::GetKernelConnectionOptions, dbgeng/IDebugClient5::GetKernelConnectionOptions, dbgeng/IDebugClient::GetKernelConnectionOptions, debugger.getkernelconnectionoptions
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
-	IDebugClient.GetKernelConnectionOptions
-	IDebugClient2.GetKernelConnectionOptions
-	IDebugClient3.GetKernelConnectionOptions
-	IDebugClient4.GetKernelConnectionOptions
-	IDebugClient5.GetKernelConnectionOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetKernelConnectionOptions method
The <b>GetKernelConnectionOptions</b>  method returns the connection options for the current kernel target.

## Syntax

````
HRESULT GetKernelConnectionOptions(
  [out, optional] PSTR   Buffer,
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

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538145">AttachKernel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetKernelConnectionOptions method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>