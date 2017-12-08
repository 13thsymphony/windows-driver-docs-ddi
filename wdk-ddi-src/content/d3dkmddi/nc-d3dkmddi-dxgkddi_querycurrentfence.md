---
UID: NC.d3dkmddi.DXGKDDI_QUERYCURRENTFENCE
title: DXGKDDI_QUERYCURRENTFENCE
author: windows-driver-content
description: The DxgkDdiQueryCurrentFence function queries about the latest completed submission fence identifier in the hardware command execution unit.
old-location: display\dxgkddiquerycurrentfence.htm
old-project: display
ms.assetid: 0ca4d42f-3036-4b81-91a4-fbce7ac891fe
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiQueryCurrentFence
req.alt-loc: D3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DXGKDDI_QUERYCURRENTFENCE callback



## -description
The <i>DxgkDdiQueryCurrentFence</i> function queries about the latest completed submission fence identifier in the hardware command execution unit.


## -prototype

````
DXGKDDI_QUERYCURRENTFENCE DxgkDdiQueryCurrentFence;

NTSTATUS  APIENTRY DxgkDdiQueryCurrentFence(
   const HANDLE                    hAdapter,
         DXGKARG_QUERYCURRENTFENCE *pCurrentFence
)
{ ... }
````


## -parameters

### -param hAdapter 

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

### -param pCurrentFence 

[in/out] A pointer to a <a href="display.dxgkarg_querycurrentfence">DXGKARG_QUERYCURRENTFENCE</a> structure that contains information about the current fence data. 

## -returns
<i>DxgkDdiQueryCurrentFence</i> returns STATUS_SUCCESS, or an appropriate error result if the fence data is not successfully retrieved.

## -remarks
A <i>fence</i> is an instruction that contains 64 bits of data and an address. The display miniport driver can insert a fence in the direct memory access (DMA) stream that is sent to the graphics processing unit (GPU). When the GPU reads the fence, the GPU writes the fence data at the specified fence address. However, before the GPU can write the fence data to memory, it must ensure that all of the pixels from the primitives that precede the fence instruction are retired and properly written to memory. 

Hardware that supports per-GPU-context virtual address space must support the following types of fences:

<i>Regular fences </i>are fences that can be inserted in a DMA buffer that is created in user mode. Because the content of a DMA buffer from user mode is not trusted, fences within such a DMA buffer must refer to a virtual address in the GPU context address space and not to a physical address. Access to such a virtual address is bound by the same memory validation mechanism as any other virtual address that the GPU accesses.

<i>Privileged fences</i> are fences that can be inserted only in a DMA buffer that is created (and only accessible) in kernel mode. Fences within such a DMA buffer refer to a physical address in memory. 

Note that if the fence target address was accessible in user mode, malicious software could perform a graphics operation over the memory location for the fence and therefore override the content of what the kernel expected to receive.

Note that a privileged DMA buffer can contain both regular and privileged fences. However, if a privileged DMA buffer contains a regular fence, the kernel component that generated such a DMA buffer is aware that the regular fence inside might never be accessible.

If the display miniport driver missed the last fence of a DMA buffer, the driver's <i>DxgkDdiQueryCurrentFence</i> function might be called to report the missed fence. For example, if the hardware generates a fence to memory, the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function is triggered to read the memory. However, if the fence's data is not available when the driver attempts to read the data (for example, if there is a defective chipset), the fence is typically reported at the next interrupt, unless interrupts were stopped. If interrupts were stopped and the DirectX graphics kernel subsystem waits too long for a fence, the subsystem calls the driver's <i>DxgkDdiQueryCurrentFence</i> function to verify the current fence and determine any pending fence that it might have missed.

Before the display miniport driver returns from a call to <i>DxgkDdiQueryCurrentFence</i>, if the latest hardware-completed submission fence identifier has not yet been reported, the driver must call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function to report the fence. To implement this functionality, the driver:

Tracks which fence was last reported to the operating system.

Raises IRQL to device interrupt. To raise IRQL to interrupt level, the driver can call the <a href="..\dispmprt\nc-dispmprt-dxgkcb_synchronize_execution.md">DxgkCbSynchronizeExecution</a> function to synchronize with its <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function.

At device interrupt IRQL, compares the last reported fence with the latest hardware-completed fence.

At device interrupt IRQL, calls <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> only when the latest hardware completed fence is newer than the last reported fence.

<i>DxgkDdiQueryCurrentFence</i> should be made pageable.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkarg_querycurrentfence">DXGKARG_QUERYCURRENTFENCE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_synchronize_execution.md">DxgkCbSynchronizeExecution</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERYCURRENTFENCE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
