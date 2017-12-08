---
UID: NS.DXGIDDI.DXGI_DDI_BASE_ARGS
title: DXGI_DDI_BASE_ARGS
author: windows-driver-content
description: The DXGI_DDI_BASE_ARGS structure contains Microsoft DirectX Graphics Infrastructure (DXGI) basic device driver interface (DDI) device creation arguments.
old-location: display\dxgi_ddi_base_args.htm
old-project: display
ms.assetid: e835edb9-7a7e-4258-957a-49877b1ed562
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DXGI_DDI_BASE_ARGS, DXGI_DDI_BASE_ARGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_BASE_ARGS
req.alt-loc: dxgiddi.h
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
---

# DXGI_DDI_BASE_ARGS structure



## -description
The <b>DXGI_DDI_BASE_ARGS</b> structure contains Microsoft DirectX Graphics Infrastructure (DXGI) basic device driver interface (DDI) device creation arguments.


## -syntax

````
typedef struct DXGI_DDI_BASE_ARGS {
  DXGI_DDI_BASE_CALLBACKS *pDXGIBaseCallbacks;
  union {
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
    DXGI1_3_DDI_BASE_FUNCTIONS *pDXGIDDIBaseFunctions4;
#endif 
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN8)
    DXGI1_2_DDI_BASE_FUNCTIONS *pDXGIDDIBaseFunctions3;
#endif 
    DXGI1_1_DDI_BASE_FUNCTIONS *pDXGIDDIBaseFunctions2;
    DXGI_DDI_BASE_FUNCTIONS    *pDXGIDDIBaseFunctions;
  };
} DXGI_DDI_BASE_ARGS;
````


## -struct-fields

### -field pDXGIBaseCallbacks

[in] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_callbacks.md">DXGI_DDI_BASE_CALLBACKS</a> structure that contains a table of Microsoft Direct3D runtime callback functions that the driver can use to access kernel services.

### -field pDXGIDDIBaseFunctions4

[in/out] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi1_3_ddi_base_functions.md">DXGI1_3_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.
 Supported starting with Windows 8.1.

### -field pDXGIDDIBaseFunctions3

[in/out] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi1_2_ddi_base_functions.md">DXGI1_2_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.
Supported starting with Windows 8.

### -field pDXGIDDIBaseFunctions2

[in/out] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi1_1_ddi_base_functions.md">DXGI1_1_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.
 Supported starting with Windows 7.

### -field pDXGIDDIBaseFunctions

[in/out] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_functions.md">DXGI_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

## -remarks


## -requirements
<table>
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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_callbacks.md">DXGI_DDI_BASE_CALLBACKS</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_functions.md">DXGI_DDI_BASE_FUNCTIONS</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi1_1_ddi_base_functions.md">DXGI1_1_DDI_BASE_FUNCTIONS</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi1_2_ddi_base_functions.md">DXGI1_2_DDI_BASE_FUNCTIONS</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi1_3_ddi_base_functions.md">DXGI1_3_DDI_BASE_FUNCTIONS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_BASE_ARGS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
