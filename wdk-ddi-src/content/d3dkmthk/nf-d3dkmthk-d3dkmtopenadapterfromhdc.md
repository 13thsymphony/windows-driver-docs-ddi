---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromHdc
title: D3DKMTOpenAdapterFromHdc function
author: windows-driver-content
description: The D3DKMTOpenAdapterFromHdc function maps a device context handle (HDC) to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
old-location: display\d3dkmtopenadapterfromhdc.htm
old-project: display
ms.assetid: f54951fe-c79e-435e-9f31-9c39da26da6c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOpenAdapterFromHdc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTOpenAdapterFromHdc
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenAdapterFromHdc function



## -description
The <b>D3DKMTOpenAdapterFromHdc</b> function maps a device context handle (HDC) to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.



## -syntax

````
NTSTATUS D3DKMTOpenAdapterFromHdc(
  _Inout_ D3DKMT_OPENADAPTERFROMHDC *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openadapterfromhdc.md">D3DKMT_OPENADAPTERFROMHDC</a> structure that describes the parameters that are required to perform the mapping.


## -returns
<b>D3DKMTOpenAdapterFromHdc</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The mapping was performed successfully.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The kernel ran out of the resources that would enable it to open another handle.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks
A graphics adapter corresponds to a video card. A monitor output corresponds to a head on a video card. A system with a single video card contains only one adapter. However, if the video card supports multiple heads, it supports outputting to multiple monitors.

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTOpenAdapterFromHdc</b> to retrieve the graphics adapter handle and the output for the primary monitor from the HDC.


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openadapterfromhdc.md">D3DKMT_OPENADAPTERFROMHDC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenAdapterFromHdc function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

