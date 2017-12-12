---
UID: NC.d3d10umddi.PFND3D11_1DDI_DISCARD
title: PFND3D11_1DDI_DISCARD
author: windows-driver-content
description: Discards (evicts) an allocation from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\discard_d3d11_1_.htm
old-project: display
ms.assetid: d94234ab-712b-4449-96de-16b9e310d250
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Discard(D3D11_1)
req.alt-loc: D3d10umddi.h
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

# PFND3D11_1DDI_DISCARD callback



## -description
Discards (evicts) an allocation from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.



## -prototype

````
PFND3D11_1DDI_DISCARD Discard(D3D11_1);

VOID APIENTRY* Discard(D3D11_1)(
                 D3D10DDI_HDEVICE    hDevice,
                 D3D11DDI_HANDLETYPE HandleType,
                 VOID                *hResourceOrView,
  _In_opt_ const D3D10_DDI_RECT      *pRects,
                 UINT                NumRects
)
{ ... }
````


## -parameters

### -param hDevice 

A handle to the display device (graphics context).


### -param HandleType 

A value, of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>, that identifies the context handle type.


### -param hResourceOrView 

A pointer to a handle to the resource or to the view that is to be discarded.


### -param pRects [in, optional]

An optional array of <a href="display.rect">RECT</a> structures for the rectangles in the resource view to discard. If <b>NULL</b>, the <i>Discard(D3D11_1)</i> function discards the entire surface.


### -param NumRects 

The number of rectangles in the array that the  <i>pRects</i> parameter specifies.


## -returns
This callback function does not return a value.


## -remarks
The D3D10_DDI_RECT structure is defined as a <a href="display.rect">RECT</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_devicefuncs~r1.md">D3D11_1DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_DISCARD callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

