---
UID: NC:d3dumddi.PFND3DDDI_CREATEDECODEDEVICE
title: PFND3DDDI_CREATEDECODEDEVICE
author: windows-driver-content
description: The CreateDecodeDevice function creates a Microsoft DirectX Video Acceleration (DirectX VA) decode device that is used to decode video.
old-location: display\createdecodedevice.htm
old-project: display
ms.assetid: 4d9a062a-2fdf-4e55-a335-c03c5d5665ff
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateDecodeDevice
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_CREATEDECODEDEVICE callback



## -description
The <b>CreateDecodeDevice</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) decode device that is used to decode video. 



## -prototype

````
PFND3DDDI_CREATEDECODEDEVICE CreateDecodeDevice;

__checkReturn HRESULT APIENTRY CreateDecodeDevice(
  _In_    HANDLE                       hDevice,
  _Inout_ D3DDDIARG_CREATEDECODEDEVICE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdecodedevice.md">D3DDDIARG_CREATEDECODEDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.


## -returns
<b>CreateDecodeDevice</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The DirectX VA decode device is successfully created.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a> could not allocate the required memory for it to complete.

 


## -remarks


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
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdecodedevice.md">D3DDDIARG_CREATEDECODEDEVICE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydecodedevice.md">DestroyDecodeDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATEDECODEDEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

