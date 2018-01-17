---
UID: NS:d3dumddi._D3DDDIARG_LOCKASYNC
title: _D3DDDIARG_LOCKASYNC
author: windows-driver-content
description: The D3DDDIARG_LOCKASYNC structure describes a resource or a surface within the resource to lock.
old-location: display\d3dddiarg_lockasync.htm
old-project: display
ms.assetid: dfe2ab95-e494-430d-81c7-8f209a37024f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_LOCKASYNC, D3DDDIARG_LOCKASYNC
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
req.alt-api: D3DDDIARG_LOCKASYNC
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
req.typenames: D3DDDIARG_LOCKASYNC
---

# _D3DDDIARG_LOCKASYNC structure



## -description
The D3DDDIARG_LOCKASYNC structure describes a resource or a surface within the resource to lock. 



## -syntax

````
typedef struct _D3DDDIARG_LOCKASYNC {
  HANDLE                 hResource;
  UINT                   SubResourceIndex;
  D3DDDI_LOCKASYNCFLAGS  Flags;
  union {
    D3DDDIRANGE Range;
    RECT        Area;
    D3DDDIBOX   Box;
  };
  HANDLE                 hCookie;
  VOID                   *pSurfData;
  UINT                   Pitch;
  UINT                   SlicePitch;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7)
  D3DGPU_VIRTUAL_ADDRESS GpuVirtualAddress;
#endif 
} D3DDDIARG_LOCKASYNC;
````


## -struct-fields

### -field hResource

[in] A handle to the resource to be locked. 


### -field SubResourceIndex

[in] The zero-based index into the resource that <b>hResource</b> specifies. This index indicates the subresource or surface to be locked.


### -field Flags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockasyncflags.md">D3DDDI_LOCKASYNCFLAGS</a> structure that indicates, in bit-field flags, how to lock the resource. 

<div class="alert"><b>Note</b>    Some flags are mutually exclusive with other flags. For more information, see the following Remarks section.</div>
<div> </div>

### -field Range

[in] A D3DDDIRANGE structure that describes the subrange of the linear resource to lock, if the <b>RangeValid</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.


### -field Area

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the subrectangle of the surface to lock, if the <b>AreaValid</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.


### -field Box

[in] A D3DDDIBOX structure that describes the subvolume of the volume to lock, if the <b>BoxValid</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.


### -field hCookie

[out] A handle that represents the renamed resource. This handle is valid only if the <b>Discard</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies. 


### -field pSurfData

[out] A pointer to the memory region for the resource that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function returns this pointer to the Microsoft Direct3D runtime.


### -field Pitch

[out] The pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function returns this pitch value to the Direct3D runtime.


### -field SlicePitch

[out] The slice pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function returns this slice pitch value to the Direct3D runtime.


### -field GpuVirtualAddress

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -remarks
The members of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockasyncflags.md">D3DDDI_LOCKASYNCFLAGS</a> structure that the <b>Flags</b> member specifies must adhere to the following rules:

The <b>NoOverwrite</b> bit-field flag must not be simultaneously set with the <b>Discard</b> bit-field flag.

Only one of the <b>RangeValid</b>, <b>AreaValid</b>, and <b>BoxValid</b> bit-field flags must be set at any time.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockasyncflags.md">D3DDDI_LOCKASYNCFLAGS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_LOCKASYNC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

