---
UID: NC.d3d10umddi.PFND3D10DDI_IA_SETINDEXBUFFER
title: PFND3D10DDI_IA_SETINDEXBUFFER
author: windows-driver-content
description: The IaSetIndexBuffer function sets an index buffer for an input assembler.
old-location: display\iasetindexbuffer.htm
old-project: display
ms.assetid: 042ebb72-b794-4cb8-9d81-bd52a785f1e0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IaSetIndexBuffer
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
---

# PFND3D10DDI_IA_SETINDEXBUFFER callback



## -description
The <i>IaSetIndexBuffer</i> function sets an index buffer for an input assembler.



## -prototype

````
PFND3D10DDI_IA_SETINDEXBUFFER IaSetIndexBuffer;

VOID APIENTRY IaSetIndexBuffer(
  _In_ D3D10DDI_HDEVICE   hDevice,
  _In_ D3D10DDI_HRESOURCE hBuffer,
  _In_ DXGI_FORMAT        Format,
  _In_ UINT               Offset
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hBuffer [in]

 A handle to the index buffer to set.


### -param Format [in]

 A DXGI_FORMAT-typed value that indicates the pixel format of the index buffer. Only the DXGI_FORMAT_R16_UINT and DXGI_FORMAT_R32_UINT formats are valid; all other formats are invalid. 


### -param Offset [in]

 The offset, in bytes, into the index buffer. 


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.


## -remarks
The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>IaSetIndexBuffer</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.


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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_IA_SETINDEXBUFFER callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

