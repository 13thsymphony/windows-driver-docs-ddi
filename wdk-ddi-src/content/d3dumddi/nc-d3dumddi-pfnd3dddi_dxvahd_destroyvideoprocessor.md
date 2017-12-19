---
UID: NC.d3dumddi.PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR
title: PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR
author: windows-driver-content
description: The DestroyVideoProcessor function releases resources for a Microsoft DirectX Video Acceleration (VA) video processor.
old-location: display\destroyvideoprocessor.htm
old-project: display
ms.assetid: ea90fe17-4b79-4011-9e05-d5dbd06c0c6b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyVideoProcessor is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DestroyVideoProcessor
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

# PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR callback



## -description
The <b>DestroyVideoProcessor</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) video processor.



## -prototype

````
PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR DestroyVideoProcessor;

__checkReturn HRESULT APIENTRY DestroyVideoProcessor(
  _In_ HANDLE hDevice,
  _In_ HANDLE hVideoProcessor
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hVideoProcessor [in]

 A handle to the DirectX VA video processor that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a> function creates. 


## -returns
<b>DestroyVideoProcessor</b> should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA video processor. 


## -remarks
The <b>DestroyVideoProcessor</b> function notifies the driver to destroy the handle to the DirectX VA video processor that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a> function previously created. The driver can then release resources that are associated with the DirectX VA video processor handle.


## -requirements
<table>
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
Version

</th>
<td width="70%">
<i>DestroyVideoProcessor</i> is supported beginning with the Windows 7 operating system.

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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

