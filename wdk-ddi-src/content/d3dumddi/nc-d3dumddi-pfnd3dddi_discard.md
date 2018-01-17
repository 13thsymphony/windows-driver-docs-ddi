---
UID: NC:d3dumddi.PFND3DDDI_DISCARD
title: PFND3DDDI_DISCARD
author: windows-driver-content
description: Discards (evicts) a set of subresources from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\discard.htm
old-project: display
ms.assetid: F3EC7AAE-9DB8-43A1-B756-5F5C91F8372E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Discard
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
req.typenames: *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
---

# PFND3DDDI_DISCARD callback



## -description
Discards (evicts) a set of subresources from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.



## -prototype

````
PFND3DDDI_DISCARD Discard;

_Check_return_ HRESULT APIENTRY* Discard(
  _In_       HANDLE            hDevice,
  _In_ const D3DDDIARG_DISCARD *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_discard.md">D3DDDIARG_DISCARD</a> structure that defines the set of subresources that is to be discarded.


## -returns

       Returns S_OK if successful, or an appropriate error result if the operation is not successful.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_discard.md">D3DDDIARG_DISCARD</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DISCARD callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

