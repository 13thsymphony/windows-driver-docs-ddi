---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES
title: DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES
author: windows-driver-content
description: The pfnGetNumModes function returns the number of source modes in a specified VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfngetnummodes.htm
old-project: display
ms.assetid: abdc053c-45da-4af3-84c1-7eeb4a2856cb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_UPDATEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnGetNumModes
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES callback



## -description
The <b>pfnGetNumModes</b> function returns the number of source modes in a specified VidPN source mode set.



## -prototype

````
DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES pfnGetNumModes;

NTSTATUS APIENTRY pfnGetNumModes(
  _In_  const D3DKMDT_HVIDPNSOURCEMODESET hVidPnSourceModeSet,
  _Out_       SIZE_T CONST                *pNumSourceModes
)
{ ... }
````


## -parameters

### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param pNumSourceModes [out]

[out] A pointer to a SIZE_T-typed variable that receives the number of source modes in the set.


## -returns
The <b>pfnGetNumModes</b> function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.

 


## -remarks
The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

