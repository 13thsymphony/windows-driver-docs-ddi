---
UID: NS:d3d10umddi.D3D10DDIARG_OPENADAPTER
title: D3D10DDIARG_OPENADAPTER
author: windows-driver-content
description: The D3D10DDIARG_OPENADAPTER structure describes the graphics adapter object.
old-location: display\d3d10ddiarg_openadapter.htm
old-project: display
ms.assetid: ac1bf173-8c18-4bb4-9a85-79b59f27ee55
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10DDIARG_OPENADAPTER, D3D10DDIARG_OPENADAPTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDIARG_OPENADAPTER
req.alt-loc: d3d10umddi.h
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
req.typenames: D3D10DDIARG_OPENADAPTER
---

# D3D10DDIARG_OPENADAPTER structure



## -description
The D3D10DDIARG_OPENADAPTER structure describes the graphics adapter object.



## -syntax

````
typedef struct D3D10DDIARG_OPENADAPTER {
  D3D10DDI_HRTADAPTER           hRTAdapter;
  D3D10DDI_HADAPTER             hAdapter;
  UINT                          Interface;
  UINT                          Version;
  const D3DDDI_ADAPTERCALLBACKS *pAdapterCallbacks;
  union {
    D3D10DDI_ADAPTERFUNCS   *pAdapterFuncs;
#if D3D10DDI_MINOR_HEADER_VERSION >= 2 || D3D11DDI_MINOR_HEADER_VERSION >= 1
    D3D10_2DDI_ADAPTERFUNCS *pAdapterFuncs_2;
#endif 
  };
} D3D10DDIARG_OPENADAPTER;
````


## -struct-fields

### -field hRTAdapter

[in] A handle to the graphics adapter object that specifies the handle that the driver should use to query for graphics adapter capabilities when the driver calls the Microsoft Direct3D runtime-supplied <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a> callback function. 


### -field hAdapter

[out] A handle to the graphics adapter object that specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the graphics adapter object. The driver generates a unique handle and passes it back to the Direct3D runtime. 


### -field Interface

[in] The Direct3D interface version. The high 16 bits store the major release number (such as 10, 11, and so on); the low 16 bits store the minor release number (such as 0, 1, 2, and so on). The minor release number will be increased when a change to the interface is released.


### -field Version

[in] A number that the driver can use to identify when the Direct3D runtime was built. The high 16 bits represent the build number; the low 16 bits represent the revision number. 

The driver is required only to monitor the high 16 bits. The driver should ensure that the runtime build version that is passed in is greater than or equal to the current build version of the driver. The driver should return a failure from its <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10</a> function if the passed in build version is incompatible. 


### -field pAdapterCallbacks

[in] A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_adaptercallbacks.md">D3DDDI_ADAPTERCALLBACKS</a> structure that contains the Direct3D runtime-supplied <b>pfnQueryAdapterInfoCb</b> callback function that the driver can use.


### -field pAdapterFuncs

[out] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_adapterfuncs.md">D3D10DDI_ADAPTERFUNCS</a> structure that contains a table of user-mode display driver adapter-specific functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver about operations that are specific to the graphics adapter.


### -field pAdapterFuncs_2

Supported in Windows 7 and later versions.

[out] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddi_adapterfuncs.md">D3D10_2DDI_ADAPTERFUNCS</a> structure that contains a table of user-mode display driver adapter-specific functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver about operations that are specific to the graphics adapter.


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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_adapterfuncs.md">D3D10DDI_ADAPTERFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddi_adapterfuncs.md">D3D10_2DDI_ADAPTERFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_adaptercallbacks.md">D3DDDI_ADAPTERCALLBACKS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_OPENADAPTER structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

