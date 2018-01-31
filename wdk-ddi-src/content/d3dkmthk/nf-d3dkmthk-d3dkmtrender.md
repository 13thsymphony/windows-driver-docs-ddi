---
UID : NF:d3dkmthk.D3DKMTRender
title : D3DKMTRender function
author : windows-driver-content
description : The D3DKMTRender function submits the current command buffer to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location : display\d3dkmtrender.htm
old-project : display
ms.assetid : 8720db3f-aafc-4657-a0cd-3068760855a3
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : OpenGL_Functions_d24fbe14-3271-47f8-9268-8946b599b32a.xml, d3dkmthk/D3DKMTRender, D3DKMTRender function [Display Devices], D3DKMTRender, display.d3dkmtrender
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Gdi32.lib
req.dll : Gdi32.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_DRIVERVERSION
---


# D3DKMTRender function
The <b>D3DKMTRender</b> function submits the current command buffer to the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>).

## Syntax

````
NTSTATUS APIENTRY D3DKMTRender(
  _Inout_ D3DKMT_RENDER *pData
);
````

## Parameters

This function has no parameters.

## Return Value

<b>D3DKMTRender</b> returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The command buffer was successfully submitted.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display context was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The OpenGL ICD detected an invalid handle in the command buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGED_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current CPU process).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ILLEGAL_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> detected instructions that could not be supported by graphics hardware.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> detected data or instruction underrun or overrun. That is, less or more instructions or data were received than were expected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_CANT_RENDER_LOCKED_ALLOCATION</b></dt>
</dl>
</td>
<td width="60%">
The video memory manager detected references to a locked allocation in the allocation list. Note that the video memory manager returns this error only if it could not reposition the allocation to an AGP or system memory segment.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_ALLOCATION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The primary surface handle was invalidated because of a display mode change.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
An error occurred on the rendering device context that the <b>hContext</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a> specifies. 

<div class="alert"><b>Note</b>    This error code does not indicate the initiation of a Timeout Detection and Recovery (TDR) process or that the GPU stopped responding.</div>
<div> </div>
For example, the DirectX graphics kernel subsystem puts a device into an error state if the display miniport driver indicated that a DMA buffer that was submitted from this device caused a fault or if the video memory manager could not page-in all of the allocations that are required for a DMA buffer even after splitting the DMA buffer. After a device is in an error state, it cannot perform any more operations and must be destroyed and recreated. The ICD can call the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdevicestate.md">D3DKMTGetDeviceState</a> function to determine a more precise reason for the error. 

</td>
</tr>
</table> 

This function might also return other <b>NTSTATUS</b> values.

## Remarks

A command buffer typically contains many graphics commands.  

If <b>D3DKMTRender</b> returns <b>STATUS_GRAPHICS_ALLOCATION_INVALID</b>, the OpenGL ICD should re-open or re-create the primary handle, replace all references in the command buffer to the previous handle with the new handle, and then call <b>D3DKMTRender</b> again to resubmit the buffer.

After a call to <b>D3DKMTRender</b>, the OpenGL ICD should determine the base address and size of the command buffer that it should use for its next submission from the values that are returned in the <b>pCommandBuffer</b> and <b>CommandBufferSize</b> members of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a> structure that is pointed to by the <i>pData</i> parameter.

For a device that uses guaranteed DMA buffer contract mode (for more information about this mode, see <a href="https://msdn.microsoft.com/fee6f7eb-157b-466d-b482-110a48045283">Using the Guaranteed Contract DMA Buffer Model</a>), the size of the DMA buffer that is available to the display miniport driver to translate the command buffer at the next submission is the same as the size of the command buffer itself. For such a device, the OpenGL ICD should also determine the size of the allocation list that will be available to the display miniport driver during the translation of the command buffer at the next submission from the value that is returned in the <b>AllocationListSize</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a>. 

For devices that do not use guaranteed DMA buffer contract, the OpenGL ICD can use the information that is returned in the <b>CommandBufferSize</b> and <b>AllocationListSize</b> members to determine the size of the next DMA buffer and allocation list that will be available for translation. However, under low-memory conditions, the actual DMA buffer and allocation list that is provided to the display miniport driver might be smaller than required.

If the OpenGL ICD detects that most of the command buffer flushes are because the driver runs out of space in the command buffer or allocation list, the driver can request for them to be resized. To resize the command buffer, the driver sets the <b>ResizeCommandBuffer</b> bit-field flag in the <b>Flags</b> member of D3DKMT_RENDER and puts the requested size in the <b>CommandBufferSize</b> member of D3DKMT_RENDER. Similarly, to resize the allocation list, the driver sets the <b>ResizeAllocationList</b> bit-field flag in the <b>Flags</b> member of D3DKMT_RENDER and puts the requested number of elements in the <b>AllocationListSize</b> member of D3DKMT_RENDER.
<div class="alert"><b>Note</b>    Even though the driver can request for resizing of both the command buffer and the allocation list, the video memory manager might not be able to comply. Therefore, if the call to <b>D3DKMTRender</b> is successful, the driver should verify the values that are returned in the <b>pCommandBuffer</b>, <b>CommandBufferSize</b>, and <b>AllocationListSize</b> members.<p class="note">However, if the call to <b>D3DKMTRender</b> fails, the driver determines that the command buffer, the allocation list, or both were not resized. Therefore, the driver should not process the values that are returned in the <b>pCommandBuffer</b>, <b>CommandBufferSize</b>, and <b>AllocationListSize</b> members because they are invalid.

</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdevicestate.md">D3DKMTGetDeviceState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTRender function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>