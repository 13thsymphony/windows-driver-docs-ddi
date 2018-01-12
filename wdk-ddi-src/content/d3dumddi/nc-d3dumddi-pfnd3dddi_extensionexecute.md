---
UID: NC:d3dumddi.PFND3DDDI_EXTENSIONEXECUTE
title: PFND3DDDI_EXTENSIONEXECUTE
author: windows-driver-content
description: The ExtensionExecute function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.
old-location: display\extensionexecute.htm
old-project: display
ms.assetid: a3f73651-bfff-48fa-aa61-477b8af7fa07
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
req.alt-api: ExtensionExecute
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

# PFND3DDDI_EXTENSIONEXECUTE callback



## -description
The <i>ExtensionExecute</i> function performs an operation by using the given Microsoft DirectX Video Accelerator (VA) extension device.



## -prototype

````
PFND3DDDI_EXTENSIONEXECUTE ExtensionExecute;

__checkReturn HRESULT APIENTRY ExtensionExecute(
  _In_       HANDLE                     hDevice,
  _In_ const D3DDDIARG_EXTENSIONEXECUTE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_extensionexecute.md">D3DDDIARG_EXTENSIONEXECUTE</a> structure that describes the DirectX VA operation to perform.


## -returns
<i>ExtensionExecute</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The DirectX VA operation is successfully performed.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>ExtensionExecute</i> could not allocate the required memory for it to complete.

 


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
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_extensionexecute.md">D3DDDIARG_EXTENSIONEXECUTE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_EXTENSIONEXECUTE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

