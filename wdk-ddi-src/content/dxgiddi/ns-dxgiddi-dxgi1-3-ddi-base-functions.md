---
UID: NS.dxgiddi.DXGI1_3_DDI_BASE_FUNCTIONS
title: DXGI1_3_DDI_BASE_FUNCTIONS
author: windows-driver-content
description: Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.
old-location: display\dxgi1_3_ddi_base_functions.htm
ms.assetid: F857BA54-A572-4376-83F3-573F90033261
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI1_3_DDI_BASE_FUNCTIONS
req.alt-loc: Dxgiddi.h
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
ms.keywords: DXGI1_3_DDI_BASE_FUNCTIONS, DXGI1_3_DDI_BASE_FUNCTIONS
req.iface: 
---

# DXGI1_3_DDI_BASE_FUNCTIONS structure



## -description
<p>Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.</p>


## -syntax

````
typedef struct DXGI1_3_DDI_BASE_FUNCTIONS {
  HRESULT (__stdcall *pfnPresent)(DXGI_DDI_ARG_PRESENT*);
  HRESULT (__stdcall *pfnGetGammaCaps)(DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS*);
  HRESULT (__stdcall *pfnSetDisplayMode)(DXGI_DDI_ARG_SETDISPLAYMODE*);
  HRESULT (__stdcall *pfnSetResourcePriority)(DXGI_DDI_ARG_SETRESOURCEPRIORITY*);
  HRESULT (__stdcall *pfnQueryResourceResidency)(DXGI_DDI_ARG_QUERYRESOURCERESIDENCY*);
  HRESULT (__stdcall *pfnRotateResourceIdentities)(DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES*);
  HRESULT (__stdcall *pfnBlt)(DXGI_DDI_ARG_BLT*);
  HRESULT (__stdcall *pfnResolveSharedResource)(DXGI_DDI_ARG_RESOLVESHAREDRESOURCE*);
  HRESULT (__stdcall *pfnBlt1)(DXGI_DDI_ARG_BLT1*);
  HRESULT (__stdcall *pfnOfferResources)(DXGI_DDI_ARG_OFFERRESOURCES*);
  HRESULT (__stdcall *pfnReclaimResources)(DXGI_DDI_ARG_RECLAIMRESOURCES*);
  HRESULT (__stdcall *pfnGetMultiPlaneOverlayCaps)(DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS*);
  HRESULT (__stdcall *pfnGetMultiplaneOverlayGroupCaps)(DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS *pfnGetMultiplaneOverlayGroupCaps);
  HRESULT (__stdcall *pfnReserved1)( void*);
  HRESULT (__stdcall *pfnPresentMultiPlaneOverlay)(DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY *pfnPresentMultiPlaneOverlay);
  HRESULT (__stdcall *pfnReserved2)(void*);
  HRESULT (__stdcall *pfnPresent1)(DXGI_DDI_ARG_PRESENT1*);
  HRESULT (__stdcall *pfnCheckPresentDurationSupport)(DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT*);
} DXGI1_3_DDI_BASE_FUNCTIONS;
````


## -struct-fields
<dl>

### -field <b>pfnPresent</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function.</p>
</dd>

### -field <b>pfnGetGammaCaps</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a> function.</p>
</dd>

### -field <b>pfnSetDisplayMode</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a> function.</p>
</dd>

### -field <b>pfnSetResourcePriority</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a> function.</p>
</dd>

### -field <b>pfnQueryResourceResidency</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569224">QueryResourceResidencyDXGI</a> function.</p>
</dd>

### -field <b>pfnRotateResourceIdentities</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569514">RotateResourceIdentitiesDXGI</a> function.</p>
</dd>

### -field <b>pfnBlt</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> function.</p>
</dd>

### -field <b>pfnResolveSharedResource</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569488">ResolveSharedResourceDXGI</a> function.</p>
</dd>

### -field <b>pfnBlt1</b>

<dd>
<p>A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406235">Blt1DXGI</a> function.</p>
</dd>

### -field <b>pfnOfferResources</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/2E85EFB6-6116-4FE7-97E0-547FFD61B511">pfnOfferResources</a> function.</p>
</dd>

### -field <b>pfnReclaimResources</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> function.</p>
</dd>

### -field <b>pfnGetMultiPlaneOverlayCaps</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265493">pfnGetMultiPlaneOverlayCaps</a> function.</p>
</dd>

### -field <b>pfnGetMultiplaneOverlayGroupCaps</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265494">pfnGetMultiplaneOverlayGroupCaps</a> function.</p>
</dd>

### -field <b>pfnReserved1</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>pfnPresentMultiPlaneOverlay</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/C6EB96AC-0D5B-4D75-9B44-B1744F6A4360">pfnPresentMultiplaneOverlay (DXGI)</a> function.</p>
</dd>

### -field <b>pfnReserved2</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>pfnPresent1</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a> function.</p>
</dd>

### -field <b>pfnCheckPresentDurationSupport</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/D54A1BFB-7EAC-4172-854D-23A9EB9B0C76">pfnCheckPresentDurationSupport(DXGI)</a> function.</p>
</dd>
</dl>

## -remarks
<p>For more info on how to use this structure, see <a href="https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a">Supporting the DXGI DDI</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>WDDM 1.3 and later</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557485">DXGI_DDI_BASE_ARGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557492">DXGI_DDI_BASE_FUNCTIONS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451215">DXGI1_2_DDI_BASE_FUNCTIONS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI1_3_DDI_BASE_FUNCTIONS structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
