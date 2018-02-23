---
UID: NF:dbgeng.IDebugClient5.AttachKernelWide
title: IDebugClient5::AttachKernelWide method
author: windows-driver-content
description: The AttachKernelWide method connects the debugger engine to a kernel target.
old-location: debugger\attachkernelwide.htm
old-project: Debugger
ms.assetid: 02ddcd45-4848-402b-a0fa-5223b8fde52e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: AttachKernelWide method [Windows Debugging], IDebugClient5 interface, IDebugClient5, dbgeng/IDebugClient5::AttachKernelWide, debugger.attachkernelwide, IDebugClient5 interface [Windows Debugging], AttachKernelWide method, AttachKernelWide, IDebugClient5::AttachKernelWide, AttachKernelWide method [Windows Debugging]
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
-	IDebugClient5.AttachKernelWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# AttachKernelWide method
The <b>AttachKernelWide</b> method connects the <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">debugger engine</a> to a kernel target.

## Syntax

````
HRESULT AttachKernelWide(
  [in]           ULONG  Flags,
  [in, optional] PCWSTR ConnectOptions
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





#### DEBUG_ATTACH_KERNEL_CONNECTION

<i>ConnectOptions</i> will be interpreted the same way as the options that follow the <b>-k</b> switch on the WinDbg and KD command lines.  Environment variables affect <i>ConnectOptions</i> in the same way they affect the <b>-k</b> switch.  



#### DEBUG_ATTACH_EXDI_DRIVER

eXDI drivers are not described in this documentation.  If you have an eXDI interface to your hardware probe or hardware simulator, please contact Microsoft for debugging information.


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

<div class="alert"><b>Note</b>    The engine doesn't completely attach to the kernel until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> method has been called.  Only after the kernel has generated an event -- for example, the initial breakpoint -- does it become available in the debugger session.</div>
<div> </div>
For more information about connecting to live kernel-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552005">Live Kernel-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546970">GetKernelConnectionOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546970">GetKernelConnectionOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551088">IsKernelDebuggerEnabled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient5::AttachKernelWide method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>