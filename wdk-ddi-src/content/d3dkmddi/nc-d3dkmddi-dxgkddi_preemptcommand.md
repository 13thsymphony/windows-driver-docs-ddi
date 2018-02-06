---
UID: NC:d3dkmddi.DXGKDDI_PREEMPTCOMMAND
title: DXGKDDI_PREEMPTCOMMAND
author: windows-driver-content
description: The DxgkDdiPreemptCommand function preempts a direct memory access (DMA) buffer that was previously submitted to and currently queued in the hardware command execution unit.
old-location: display\dxgkddipreemptcommand.htm
old-project: display
ms.assetid: 8cea02d4-f25e-4ff4-8c9e-aa360a764c4b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddipreemptcommand, DxgkDdiPreemptCommand callback function [Display Devices], DxgkDdiPreemptCommand, DXGKDDI_PREEMPTCOMMAND, DXGKDDI_PREEMPTCOMMAND, d3dkmddi/DxgkDdiPreemptCommand, DmFunctions_a378e47e-622c-41bf-95e7-21e4088d7026.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiPreemptCommand
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_PREEMPTCOMMAND function
The <i>DxgkDdiPreemptCommand</i> function preempts a direct memory access (DMA) buffer that was previously submitted to and currently queued in the hardware command execution unit.

## Syntax

```
DXGKDDI_PREEMPTCOMMAND DxgkddiPreemptcommand;

NTSTATUS DxgkddiPreemptcommand(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_PREEMPTCOMMAND pPreemptCommand
)
{...}
```

## Parameters

`hAdapter`

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`pPreemptCommand`

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_preemptcommand.md">DXGKARG_PREEMPTCOMMAND</a> structure that describes the command that is used to preempt a DMA buffer previously submitted to the hardware command execution unit.


## Return Value

Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.

## Remarks

If the driver determines that the hardware is already finished processing all of the submitted DMA buffers--and that the hardware informed the graphics processing unit (GPU) scheduler about the completions--when its <i>DxgkDdiPreemptCommand</i> function is called to preempt the DMA buffers, the driver should perform the following operations instead of submitting the preempt fence that is identified by the <b>PreemptionFenceId</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_preemptcommand.md">DXGKARG_PREEMPTCOMMAND</a> to the hardware:
<ul>
<li>
Raise IRQL to interrupt level. For example, the driver can call the <a href="..\dispmprt\nc-dispmprt-dxgkcb_synchronize_execution.md">DxgkCbSynchronizeExecution</a> function to synchronize with its <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function.

</li>
<li>
Inform the GPU scheduler about the preemption information. The driver can either call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function directly or call its <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function (for example, if the driver must perform other updates as well).

Note that the GPU scheduler handles instances where the hardware has stopped responding because of Timeout Detection and Recovery (TDR) work.

</li>
</ul>If the driver returns an error code, the Microsoft DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.
<ol>
<li>0x2</li>
<li>The NTSTATUS error code returned from the failed driver call</li>
<li>A pointer to the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_preemptcommand.md">DXGKARG_PREEMPTCOMMAND</a> structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol><i>DxgkDdiPreemptCommand</i> should be made nonpageable because it runs at IRQL = DISPATCH_LEVEL

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_preemptcommand.md">DXGKARG_PREEMPTCOMMAND</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>

<a href="..\dispmprt\nc-dispmprt-dxgkcb_synchronize_execution.md">DxgkCbSynchronizeExecution</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_PREEMPTCOMMAND callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>