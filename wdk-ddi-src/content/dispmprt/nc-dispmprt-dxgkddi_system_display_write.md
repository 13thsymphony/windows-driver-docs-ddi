---
UID: NC.dispmprt.DXGKDDI_SYSTEM_DISPLAY_WRITE
title: DXGKDDI_SYSTEM_DISPLAY_WRITE
author: windows-driver-content
description: Called by the operating system to request the display miniport driver to write an image block to the display device.
old-location: display\dxgkddisystemdisplaywrite.htm
old-project: display
ms.assetid: 5C0F9878-522C-4DDE-A790-54C94880F119
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiSystemDisplayWrite
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
---

# DXGKDDI_SYSTEM_DISPLAY_WRITE callback



## -description
Called by the operating system to request the display miniport driver to write an image block to the display device.

Starting with Windows 8, the operating system calls this function during a bugcheck operation following a system stop error. The operating system calls this function only if the display device was previously reset through a call to <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a>.



## -prototype

````
DXGKDDI_SYSTEM_DISPLAY_WRITE DxgkDdiSystemDisplayWrite;

VOID* DxgkDdiSystemDisplayWrite(
  _In_ PVOID MiniportDeviceContext,
  _In_ PVOID Source,
  _In_ UINT  SourceWidth,
  _In_ UINT  SourceHeight,
  _In_ UINT  SourceStride,
  _In_ UINT  PositionX,
  _In_ UINT  PositionY
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




### -param Source [in]

A pointer to the start address of the source image to be written to the bugcheck screen that displays information about the system stop error.


### -param SourceWidth [in]

A UINT value that specifies the width, in units of pixels, of the specified source image.


### -param SourceHeight [in]

A UINT value that specifies the height, in units of pixels, of the specified source image.


### -param SourceStride [in]

A UINT value that specifies the number of bytes for each line of the specified source image.


### -param PositionX [in]

A UINT value that specifies the starting X coordinate that the specified source image should be written to on the display device.


### -param PositionY [in]

A UINT value that specifies the starting Y coordinate that the specified source image should be written to on the display device.


## -returns
This callback function does not return a value.


## -remarks
The display miniport driver must follow these guidelines when its <i>DxgkDdiSystemDisplayWrite</i> function is called:

The color format of the source image is always in the <b>D3DDDIFMT_R8G8B8</b> (24 bits per pixel) or <b>D3DDDIFMT_A8R8G8B8</b> (32 bpp) formats of the <a href="display.d3dddiformat">D3DDDIFORMAT</a> enumeration. The display miniport driver had previously set the display mode to enable write operations in this format when its <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a> was called.

The source image is in non-paged memory. The display miniport driver should write this source image to the current frame buffer starting at the positions specified by the <i>PostionX</i> and <i>PositionY</i> parameters.

	The display miniport driver should use the CPU to write the image block to the frame buffer. When the system encounters a stop error, it may have been caused by a continuous timeout detection and recovery (TDR) on the display device.  In that case, the graphics processing unit (GPU) might be in an unknown state.

For more information about TDR, see <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a>.

Windows kernel-mode functions might not be available while this function is being called.

<i>DxgkDdiSystemDisplayWrite</i> can be called at any IRQL, so it must be in nonpageable memory. <i>DxgkDdiSystemDisplayWrite</i> must not call any code that is in pageable memory and must not manipulate any data that is in pageable memory.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="display.DxgkCbAcquirePostDisplayOwnership">DxgkCbAcquirePostDisplayOwnership</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SYSTEM_DISPLAY_WRITE callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

