---
UID: NS:dxgiddi.DXGI1_3_DDI_BASE_FUNCTIONS
title: DXGI1_3_DDI_BASE_FUNCTIONS
author: windows-driver-content
description: Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.
old-location: display\dxgi1_3_ddi_base_functions.htm
old-project: display
ms.assetid: F857BA54-A572-4376-83F3-573F90033261
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGI1_3_DDI_BASE_FUNCTIONS, DXGI1_3_DDI_BASE_FUNCTIONS structure [Display Devices], display.dxgi1_3_ddi_base_functions, dxgiddi/DXGI1_3_DDI_BASE_FUNCTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	Dxgiddi.h
api_name:
-	DXGI1_3_DDI_BASE_FUNCTIONS
product:
- Windows
targetos: Windows
req.typenames: DXGI1_3_DDI_BASE_FUNCTIONS
---

# DXGI1_3_DDI_BASE_FUNCTIONS structure
Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.

## Syntax
```
typedef struct DXGI1_3_DDI_BASE_FUNCTIONS {
  HRESULT()(DXGI_DDI_ARG_PRESENT *) * pfnPresent;
  HRESULT()(DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS *) * pfnGetGammaCaps;
  HRESULT()(DXGI_DDI_ARG_SETDISPLAYMODE *) * pfnSetDisplayMode;
  HRESULT()(DXGI_DDI_ARG_SETRESOURCEPRIORITY *) * pfnSetResourcePriority;
  HRESULT()(DXGI_DDI_ARG_QUERYRESOURCERESIDENCY *) * pfnQueryResourceResidency;
  HRESULT()(DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES *) * pfnRotateResourceIdentities;
  HRESULT()(DXGI_DDI_ARG_BLT *) * pfnBlt;
  HRESULT()(DXGI_DDI_ARG_RESOLVESHAREDRESOURCE *) * pfnResolveSharedResource;
  HRESULT()(DXGI_DDI_ARG_BLT1 *) * pfnBlt1;
  HRESULT()(DXGI_DDI_ARG_OFFERRESOURCES *) * pfnOfferResources;
  HRESULT()(DXGI_DDI_ARG_RECLAIMRESOURCES *) * pfnReclaimResources;
  HRESULT()(DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS *) * pfnGetMultiplaneOverlayCaps;
  HRESULT()(DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS *) * pfnGetMultiplaneOverlayGroupCaps;
  HRESULT()(void *) * pfnReserved1;
  HRESULT()(DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY *) * pfnPresentMultiplaneOverlay;
  HRESULT()(void *) * pfnReserved2;
  HRESULT()(DXGI_DDI_ARG_PRESENT1 *) * pfnPresent1;
  HRESULT()(DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT *) * pfnCheckPresentDurationSupport;
};
```

## Members


`pfnPresent`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function.

`pfnGetGammaCaps`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a> function.

`pfnSetDisplayMode`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a> function.

`pfnSetResourcePriority`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a> function.

`pfnQueryResourceResidency`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569224">QueryResourceResidencyDXGI</a> function.

`pfnRotateResourceIdentities`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569514">RotateResourceIdentitiesDXGI</a> function.

`pfnBlt`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> function.

`pfnResolveSharedResource`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569488">ResolveSharedResourceDXGI</a> function.

`pfnBlt1`

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406235">Blt1DXGI</a> function.

`pfnOfferResources`

A pointer to the driver's <a href="https://msdn.microsoft.com/2E85EFB6-6116-4FE7-97E0-547FFD61B511">pfnOfferResources</a> function.

`pfnReclaimResources`

A pointer to the driver's <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> function.

`pfnGetMultiplaneOverlayCaps`



`pfnGetMultiplaneOverlayGroupCaps`

Called by the DXGI runtime to request that the user-mode display driver  get a group of overlay plane capabilities. Optionally implemented by WDDM 1.3 and later user-mode display drivers. 

<div class="alert"><b>Note</b>  This function is called for each of the capability groups that the driver reports.</div>
<div> </div>


#### pGroupCaps

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265375">DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS</a> structure that specifies the group of overlay plane capabilities.

`pfnReserved1`

Reserved for system use.

`pfnPresentMultiplaneOverlay`



`pfnReserved2`

Reserved for system use.

`pfnPresent1`

Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.

The <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn457714">DXGI_DDI_ARG_PRESENT1</a> structure that the <i>pPresentData</i> parameter points to is the same handle that the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function passed back to the runtime in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure. Therefore, driver writers must define the type of this handle carefully. In addition, drivers can supply different implementations of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a> function based on which DDI implementation handled the call to <i>CreateDevice(D3D10)</i>. The runtime will never mix driver handles across DDI implementations.

The <b>pDXGIContext</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/dn457714">DXGI_DDI_ARG_PRESENT1</a> is an opaque communication mechanism. The runtime passes this DXGI context to the driver. The driver should copy this DXGI context unchanged to the <b>pDXGIContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557440">DXGIDDICB_PRESENT</a> structure when the driver calls the <a href="https://msdn.microsoft.com/eefb8f2c-e460-4f9c-851d-9a97dbcd728f">pfnPresentCbDXGI</a> function.

The driver must submit all partially built render data (command buffers) using the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function, and the driver must make a single call to <a href="https://msdn.microsoft.com/eefb8f2c-e460-4f9c-851d-9a97dbcd728f">pfnPresentCbDXGI</a>. When calling either of these callbacks, the driver must follow the threading rules of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function.

<div class="alert"><b>Note</b>    When the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a> function copies sRGB-formatted content from a source surface to a non-sRGB destination surface, the driver should copy the sRGB content unchanged (that is, the driver should not perform the sRGB to linear conversion).</div>
<div> </div>
Threading rules

These rules apply whether the driver supports free threading or not:<ul>
<li>The driver indicates support for free threading by setting the <b>Caps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a> structure to <b>D3D11DDICAPS_FREETHREADED</b>. In this case:<ul>
<li>Only a single thread can be working against an HCONTEXT context handle at a time.</li>
<li>The driver must call <a href="https://msdn.microsoft.com/eefb8f2c-e460-4f9c-851d-9a97dbcd728f">pfnPresentCbDXGI</a> only when the driver’s <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a> function is called, and by the same thread that called <i>pfnPresent1(DXGI)</i>.</li>
</ul>
</li>
<li>When the driver doesn’t indicate support for free-threading, it can only call the callback functions when a thread has called into the driver. The driver also must still call the <a href="https://msdn.microsoft.com/eefb8f2c-e460-4f9c-851d-9a97dbcd728f">pfnPresentCbDXGI</a> callback within the context of <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a>.</li>
</ul>For further info on threading, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.



#### pPresentData

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn457714">DXGI_DDI_ARG_PRESENT1</a> structure that describes how to display to the destination surface.

`pfnCheckPresentDurationSupport`

A pointer to the driver's <a href="https://msdn.microsoft.com/D54A1BFB-7EAC-4172-854D-23A9EB9B0C76">pfnCheckPresentDurationSupport(DXGI)</a> function.

## Remarks
For more info on how to use this structure, see <a href="https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a">Supporting the DXGI DDI</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 and later Windows 8.1,WDDM 1.3 and later |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451215">DXGI1_2_DDI_BASE_FUNCTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557485">DXGI_DDI_BASE_ARGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557492">DXGI_DDI_BASE_FUNCTIONS</a>