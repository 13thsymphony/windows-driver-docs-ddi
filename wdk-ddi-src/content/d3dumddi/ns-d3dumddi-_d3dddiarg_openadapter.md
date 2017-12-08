---
UID: NS.D3DUMDDI._D3DDDIARG_OPENADAPTER
title: _D3DDDIARG_OPENADAPTER
author: windows-driver-content
description: The D3DDDIARG_OPENADAPTER structure contains information that describes the graphics adapter object.
old-location: display\d3dddiarg_openadapter.htm
old-project: display
ms.assetid: bfdea6dd-1f94-45ea-906c-9d17fc784a53
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDIARG_OPENADAPTER, D3DDDIARG_OPENADAPTER
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
req.alt-api: D3DDDIARG_OPENADAPTER
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
---

# _D3DDDIARG_OPENADAPTER structure



## -description
The D3DDDIARG_OPENADAPTER structure contains information that describes the graphics adapter object.


## -syntax

````
typedef struct _D3DDDIARG_OPENADAPTER {
  HANDLE                        hAdapter;
  UINT                          Interface;
  UINT                          Version;
  const D3DDDI_ADAPTERCALLBACKS *pAdapterCallbacks;
  D3DDDI_ADAPTERFUNCS           *pAdapterFuncs;
  UINT                          DriverVersion;
} D3DDDIARG_OPENADAPTER;
````


## -struct-fields

### -field hAdapter

[in/out] A handle to the graphics adapter object. On input to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a> function, <b>hAdapter</b> specifies the handle that the driver should use to query for graphics adapter capabilities when the driver calls the Microsoft Direct3D runtime-supplied <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a> callback function. 
The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a> function, <b>hAdapter</b> specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the graphics adapter object.

### -field Interface

[in] The Direct3D/DirectDraw interface version (for example, 7, 8, or 9) that opens the graphics adapter. 

### -field Version

[in] A number that the driver can use to identify when the Direct3D/DirectDraw runtime was built. For example, the driver can use the version number to differentiate between a runtime that is released with Windows Vista and a runtime that is released with a subsequent service pack, which might contain a fix that the driver requires. 

### -field pAdapterCallbacks

[in] A pointer to a <a href="display.d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a> structure that contains the Direct3D runtime-supplied <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a> callback function that the driver can use.

### -field pAdapterFuncs

[out] A pointer to a <a href="display.d3dddi_adapterfuncs">D3DDDI_ADAPTERFUNCS</a> structure that contains a table of user-mode display driver adapter-specific functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver about operations that are specific to the graphics adapter.

### -field DriverVersion

[out] The version of the Direct3D user-mode display driver's interface, which was obtained from the <i>D3dumddi.h</i> header file, that the driver was compiled with. The user-mode display driver should return D3D_UMD_INTERFACE_VERSION. 
<div class="alert"><b>Note</b>  If a user-mode driver does not support Windows 7 features (DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 7 WDK (Version 7600), make sure that the driver returns D3D_UMD_INTERFACE_VERSION_VISTA.</div>
<div> </div>

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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a>
</dt>
<dt>
<a href="display.d3dddi_adapterfuncs">D3DDDI_ADAPTERFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_OPENADAPTER structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
