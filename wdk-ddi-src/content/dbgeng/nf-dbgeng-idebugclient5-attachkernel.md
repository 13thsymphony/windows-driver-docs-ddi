---
UID : NF:dbgeng.IDebugClient5.AttachKernel
title : IDebugClient5::AttachKernel method
author : windows-driver-content
description : The AttachKernel methods connect the debugger engine to a kernel target.
old-location : debugger\attachkernel.htm
old-project : debugger
ms.assetid : eb861179-3567-4654-a702-40ee3319b27a
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugClient5, IDebugClient5::AttachKernel, AttachKernel
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugClient.AttachKernel,IDebugClient2.AttachKernel,IDebugClient3.AttachKernel,IDebugClient4.AttachKernel,IDebugClient5.AttachKernel
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# AttachKernel method
The <b>AttachKernel</b>  methods connect the <a href="debugger.d#debugger_engine#debugger_engine"><i>debugger engine</i></a> to a kernel target.

## Syntax

````
HRESULT AttachKernel(
  [in]           ULONG Flags,
  [in, optional] PCSTR ConnectOptions
);
````

## Parameters

`Flags`

Specifies the flags that control how the debugger attaches to the kernel target.  The possible values are:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_ATTACH_KERNEL_CONNECTION

</td>
<td>
Attach to the kernel on the target computer.

</td>
</tr>
<tr>
<td>
DEBUG_ATTACH_EXDI_DRIVER

</td>
<td>
Attach to a kernel by using an eXDI driver.

</td>
</tr>
</table>

`ConnectOptions`

Specifies the connection settings for communicating with the computer running the kernel target.  The interpretation of <i>ConnectOptions</i> depends on the value of <i>Flags</i>.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

For more information about connecting to live kernel-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552005">Live Kernel-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546970">GetKernelConnectionOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551088">IsKernelDebuggerEnabled</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::AttachKernel method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>