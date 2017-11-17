---
UID: NS.d3dkmthk._D3DKMT_CREATEALLOCATION
title: D3DKMT_CREATEALLOCATION
author: windows-driver-content
description: The D3DKMT_CREATEALLOCATION structure describes parameters for creating allocations.
old-location: display\d3dkmt_createallocation.htm
ms.assetid: 3e698027-23f8-4765-a4ac-955cd4b24a70
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATEALLOCATION
req.alt-loc: d3dkmthk.h
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
ms.keywords: D3DKMT_CREATEALLOCATION, D3DKMT_CREATEALLOCATION
req.iface: 
---

# D3DKMT_CREATEALLOCATION structure



## -description
<p>The D3DKMT_CREATEALLOCATION structure describes parameters for creating allocations.</p>


## -syntax

````
typedef struct _D3DKMT_CREATEALLOCATION {
  D3DKMT_HANDLE                hDevice;
  D3DKMT_HANDLE                hResource;
  D3DKMT_HANDLE                hGlobalShare;
  const VOID                   *pPrivateRuntimeData;
  UINT                         PrivateRuntimeDataSize;
  const VOID                   *pPrivateDriverData;
  UINT                         PrivateDriverDataSize;
  UINT                         NumAllocations;
  union {
    D3DDDI_ALLOCATIONINFO  *pAllocationInfo;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7))
    D3DDDI_ALLOCATIONINFO2 *pAllocationInfo2;
#endif 
  };
  D3DKMT_CREATEALLOCATIONFLAGS Flags;
  HANDLE                       hPrivateRuntimeResourceHandle;
} D3DKMT_CREATEALLOCATION;
````


## -struct-fields
<dl>

### -field <b>hDevice</b>

<dd>
<p>[in] A handle to the device that the resource or allocation is associated with.</p>
</dd>

### -field <b>hResource</b>

<dd>
<p>[in/out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations. The value in <b>hResource</b> should always be zero unless an allocation will be added to an existing resource, in which case <b>hResource</b> contains the resource handle. </p>
<p>When the <b>CreateResource</b> bit-field flag is set in the <b>Flags</b> member, the OpenGL runtime generates a unique handle and passes it back to the driver. On output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546807">D3DKMTCreateAllocation</a> function, <b>hResource</b> specifies the handle that the driver should use in subsequent OpenGL runtime calls to identify the resource. The resource handle that is returned is device-specific and is valid only when used with the device that it was created on.</p>
</dd>

### -field <b>hGlobalShare</b>

<dd>
<p>[out] A handle to the shared resource. The driver should always set the value in <b>hGlobalShare</b> to zero. </p>
<p>When the driver sets the <b>CreateShared</b> bit-field flag in <b>Flags</b> to create a shared resource, the OpenGL runtime generates a shared handle that is unique across all of the devices and passes it back to the driver in <b>hGlobalShare</b>.<div class="alert"><b>Note</b>  If you set  <b>CreateShared</b>, you must also set the <b>CreateResource</b> bit-field flag.</div>
<div> </div>
</p>
</dd>

### -field <b>pPrivateRuntimeData</b>

<dd>
<p>[in] A pointer to optional private data that can be attached to a resource for debugging purposes. This data is per resource and not per allocation.</p>
</dd>

### -field <b>PrivateRuntimeDataSize</b>

<dd>
<p>[in] The size, in bytes, of the private data that <b>pPrivateRuntimeData</b> points to.</p>
</dd>

### -field <b>pPrivateDriverData</b>

<dd>
<p>[in] A pointer to a buffer that contains optional private data that the display miniport driver might require to create the resource or allocation. The contents of the buffer typically come from the OpenGL ICD and must be in a format that the display miniport driver can process.</p>
</dd>

### -field <b>PrivateDriverDataSize</b>

<dd>
<p>[in/out] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.</p>
</dd>

### -field <b>NumAllocations</b>

<dd>
<p>[in] The number of elements in the array that <b>pAllocationInfo</b> specifies, which represents the number of allocations to create. Note that creating a resource without any allocations initially associated with it is valid; therefore, <b>NumAllocations</b> can be set to 0.</p>
</dd>

### -field <b>pAllocationInfo</b>

<dd>
<p>[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a> structures that describe specific properties for each allocation to create.</p>
</dd>

### -field <b>pAllocationInfo2</b>

<dd>
<p>[in] This member is reserved and should be set to zero.</p>
<p>This member is available beginning with Windows 7.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff547802">D3DKMT_CREATEALLOCATIONFLAGS</a> structure that identifies  attributes for creating the allocation, in bit-field flags.</p>
<div class="alert"><b>Note</b>  If  you set the <b>CreateShared</b> bit-field flag in <b>Flags</b>, you must also set the <b>CreateResource</b> bit-field flag.</div>
<div> </div>
</dd>

### -field <b>hPrivateRuntimeResourceHandle</b>

<dd>
<p>[in] An opaque handle that you can use in event tracing. This handle can be used to associate kernel-mode allocations with user-mode surface pointers when you analyze Event Tracing for Windows (ETW) event logs.</p>
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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547802">D3DKMT_CREATEALLOCATIONFLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546807">D3DKMTCreateAllocation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEALLOCATION structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
