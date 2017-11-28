---
UID: NS.d3dumddi._D3DDDIARG_CREATEDEVICE
title: D3DDDIARG_CREATEDEVICE
author: windows-driver-content
description: The D3DDDIARG_CREATEDEVICE structure contains information that describes the display device to create.
old-location: display\d3dddiarg_createdevice.htm
old-project: display
ms.assetid: 18be278c-2d69-472b-9baf-7c35f8abe879
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDIARG_CREATEDEVICE, D3DDDIARG_CREATEDEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_CREATEDEVICE
req.alt-loc: d3dumddi.h
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
req.iface: 
---

# D3DDDIARG_CREATEDEVICE structure



## -description
<p>The D3DDDIARG_CREATEDEVICE structure contains information that describes the display device to create.</p>


## -syntax

````
typedef struct _D3DDDIARG_CREATEDEVICE {
  HANDLE                       hDevice;
  UINT                         Interface;
  UINT                         Version;
  const D3DDDI_DEVICECALLBACKS *pCallbacks;
  VOID                         *pCommandBuffer;
  UINT                         CommandBufferSize;
  D3DDDI_ALLOCATIONLIST        *pAllocationList;
  UINT                         AllocationListSize;
  D3DDDI_PATCHLOCATIONLIST     *pPatchLocationList;
  UINT                         PatchLocationListSize;
  D3DDDI_DEVICEFUNCS           *pDeviceFuncs;
  D3DDDI_CREATEDEVICEFLAGS     Flags;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7)
  D3DGPU_VIRTUAL_ADDRESS       CommandBuffer;
#endif 
} D3DDDIARG_CREATEDEVICE;
````


## -struct-fields
<dl>

### -field <b>hDevice</b>

<dd>
<p>[in/out] A handle to the display device (graphics context). On input to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createdevice.md">CreateDevice</a> function, <b>hDevice</b> specifies the handle that the driver should use when it calls back into the Microsoft Direct3D runtime. </p>
<p>The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createdevice.md">CreateDevice</a> function, <b>hDevice</b> specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the display device.</p>
</dd>

### -field <b>Interface</b>

<dd>
<p>[in] The Direct3D/DirectDraw interface version (for example, 7, 8, or 9) that creates the device. </p>
</dd>

### -field <b>Version</b>

<dd>
<p>[in] A number that the driver can use to identify when the Direct3D/DirectDraw runtime was built. For example, the driver can use the version number to differentiate between a runtime that is released with Windows Vista and a runtime that is released with a subsequent service pack, which might contain a fix that the driver requires. </p>
</dd>

### -field <b>pCallbacks</b>

<dd>
<p>[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a> structure that contains a table of Direct3D runtime callback functions that the driver can use.</p>
</dd>

### -field <b>pCommandBuffer</b>

<dd>
<p>[in] Obsolete. To receive a pointer to the first buffer that the user-mode display driver can use to batch commands, the driver must first call the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function to create a context for the newly created device.</p>
</dd>

### -field <b>CommandBufferSize</b>

<dd>
<p>[in] Obsolete.</p>
</dd>

### -field <b>pAllocationList</b>

<dd>
<p>[in] Obsolete. To receive an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a> structures for the starting allocation list, the driver must first call the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function to create a context for the newly created device.</p>
</dd>

### -field <b>AllocationListSize</b>

<dd>
<p>[in] Obsolete.</p>
</dd>

### -field <b>pPatchLocationList</b>

<dd>
<p>[in] Obsolete. To receive an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a> structures for the starting patch-location list, the driver must first call the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function to create a context for the newly created device.</p>
</dd>

### -field <b>PatchLocationListSize</b>

<dd>
<p>[in] Obsolete.</p>
</dd>

### -field <b>pDeviceFuncs</b>

<dd>
<p>
      [out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.
     </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544507">D3DDDI_CREATEDEVICEFLAGS</a> structure that identifies how to create the device. </p>
</dd>

### -field <b>CommandBuffer</b>

<dd>
<p>This member is reserved and should be set to zero.</p>
<p>This member is available beginning with Windows 7.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createdevice.md">CreateDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544507">D3DDDI_CREATEDEVICEFLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="display.dxgkddicreatedevice">DxgkDdiCreateDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEDEVICE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
