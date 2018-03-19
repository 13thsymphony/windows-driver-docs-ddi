---
UID: NS:d3dkmthk._D3DKMT_PRESENT
title: "_D3DKMT_PRESENT"
author: windows-driver-content
description: The D3DKMT_PRESENT structure describes the present operation.
old-location: display\d3dkmt_present.htm
old-project: display
ms.assetid: 959d17f1-588b-4b65-a3ea-e4609aa84eed
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_PRESENT, D3DKMT_PRESENT structure [Display Devices], OpenGL_Structs_f3a9c661-7b2d-4f75-864f-c5f2a3c591ad.xml, _D3DKMT_PRESENT, d3dkmthk/D3DKMT_PRESENT, display.d3dkmt_present
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_PRESENT
product: Windows
targetos: Windows
req.typenames: D3DKMT_PRESENT
---

# _D3DKMT_PRESENT structure
The D3DKMT_PRESENT structure describes the present operation.

## Syntax
````
typedef struct _D3DKMT_PRESENT {
  union {
    D3DKMT_HANDLE hDevice;
    D3DKMT_HANDLE hContext;
  };
  HWND                           hWindow;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_HANDLE                  hSource;
  D3DKMT_HANDLE                  hDestination;
  UINT                           Color;
  RECT                           DstRect;
  RECT                           SrcRect;
  UINT                           SubRectCnt;
  const RECT                     *pSrcSubRects;
  UINT                           PresentCount;
  D3DDDI_FLIPINTERVAL_TYPE       FlipInterval;
  D3DKMT_PRESENTFLAGS            Flags;
  ULONG                          BroadcastContextCount;
  D3DKMT_HANDLE                  BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  HANDLE                         PresentLimitSemaphore;
  D3DKMT_PRESENTHISTORYTOKEN     PresentHistoryToken;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  D3DKMT_PRESENT_RGNS            *pPresentRegions;
#endif 
} D3DKMT_PRESENT;
````

## Members


`hWindow`

[in] A handle to the window that the bit-block transfer (bitblt) applies to. A value of <b>NULL</b> indicates the desktop window. The value in <b>hWindow</b> can be <b>NULL</b> unless the <b>Blt</b> or <b>ColorFill</b> bit-field flag is specified in the <b>Flags</b> member.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which to restrict displaying, if the <b>RestrictVidPnSource</b> bit-field flag is set in the <b>Flags</b> member.

If the <b>RestrictVidPnSource</b> bit-field flag is set and the <b>hWindow</b> member is <b>NULL</b>, the <b>VidPnSourceId</b> member indicates which output the full-screen bitblt is directed to If <b>RestrictVidPnSource</b> is set and <b>hWindow</b> is non-<b>NULL</b>, <b>VidPnSourceId</b> indicates to which output to restrict the windowed bit-block transfer.

`hSource`

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the system memory or primary allocation to present from, if the <b>ColorFill</b> bit-field flag is not set in the <b>Flags</b> member.

`hDestination`

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the destination allocation. <b>hDestination</b> can be zero if the destination is unknown. 

The handle in <b>hDestination</b> is valid only if the <b>Blt</b> bit-field flag is set in the <b>Flags</b> member.

If the handle in the <b>hDestination</b> member is nonzero, the <b>hDestination</b> and <b>hWindow</b> handles must refer to two different primary allocations of the same size, the device in the <b>hDevice</b> member must own the video present source that is identified by the <b>VidPnSourceId</b> member, and the <b>SrcRectValid</b> bit-field flag must be set in the <b>Flags</b> member.

`Color`

[in] The ARGB 32-bit (see the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration) color-fill or color-key value . A value for color fill is set when the <b>ColorFill</b> bit-field flag is set in the <b>Flags</b> member. A value for color key is set when either the <b>SrcColorKey</b> or <b>DstColorKey</b> bit-field flag is set in the <b>Flags</b> member. Note that only one of the <b>ColorFill</b>, <b>SrcColorKey</b>, and <b>DstColorKey</b> bit-field flags is set at any time. 

If the primary format is palettized RGB, <b>Color</b> contains the palette index rather than the D3DDDIFMT_A8R8G8B8 value from D3DDDIFORMAT.

`DstRect`

[in] The optional destination <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> for the bitblt. The destination RECT is used only if the <b>DstRectValid</b> bit-field flag is set in the <b>Flags</b> member.

`SrcRect`

[in] The optional source RECT for the bitblt. The source RECT is used only if the <b>SrcRectValid</b> bit-field flag is set in the <b>Flags</b> member.

`SubRectCnt`

[in] The number of subrectangular regions that <b>pSrcSubRects</b> points to that are specified when presenting.

`pSrcSubRects`

[in] A pointer to an array of subrectangular regions (RECTs) that are specified when presenting.

`PresentCount`

[in] The number of present operations that can be queued for the device that is specified by <b>hDevice</b>.

`FlipInterval`

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs).

`Flags`

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presentflags.md">D3DKMT_PRESENTFLAGS</a> structure that identifies, in bit-field flags, how to display. Note that the <b>ColorFill</b>, <b>SrcColorKey</b>, and <b>DstColorKey</b> bit-field flags are mutually exclusive.

`BroadcastContextCount`

[in] The number of additional contexts in the array that <b>BroadcastContext</b> specifies.

`BroadcastContext`

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the additional contexts to broadcast the current present operation to. The D3DDDI_MAX_BROADCAST_CONTEXT constant, which is defined as 64, defines the maximum number of contexts that the OpenGL ICD can broadcast the current present operation to.

Broadcasting is supported only for flip operations. To broadcast a flip operation, the display miniport driver must support memory mapped I/O (MMIO)-based flips. To indicate support of MMIO flips, the display miniport driver sets the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure when its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called.

The original context that the <b>hContext</b> member specifies and that the OpenGL ICD presents to is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the OpenGL ICD sends the present operation to the owning context (<b>hContext</b>) and broadcasts to that one additional context.

`PresentLimitSemaphore`

[in] The handle to the present-limit semaphore.

Supported starting with Windows 7.

`PresentHistoryToken`

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a> structure that identifies the type of present operation.

Supported starting with Windows 7.

`pPresentRegions`

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present_rgns.md">D3DKMT_PRESENT_RGNS</a> structure that identifies dirty and move regions.

Supported starting with Windows 8.

`Duration`



`BroadcastSrcAllocation`



`BroadcastDstAllocation`



`PrivateDriverDataSize`



`pPrivateDriverData`



`bOptimizeForComposition`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presentflags.md">D3DKMT_PRESENTFLAGS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtpresent.md">D3DKMTPresent</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present_rgns.md">D3DKMT_PRESENT_RGNS</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>