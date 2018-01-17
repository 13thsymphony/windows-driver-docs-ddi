---
UID: NS:d3dumddi._D3DDDIARG_SETDECODERENDERTARGET
title: _D3DDDIARG_SETDECODERENDERTARGET
author: windows-driver-content
description: The D3DDDIARG_SETDECODERENDERTARGET structure describes the decode render target surface.
old-location: display\d3dddiarg_setdecoderendertarget.htm
old-project: display
ms.assetid: 8903b579-8a63-42a5-9115-251f4e77ebb4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_SETDECODERENDERTARGET, D3DDDIARG_SETDECODERENDERTARGET
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
req.alt-api: D3DDDIARG_SETDECODERENDERTARGET
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
req.typenames: D3DDDIARG_SETDECODERENDERTARGET
---

# _D3DDDIARG_SETDECODERENDERTARGET structure



## -description
The D3DDDIARG_SETDECODERENDERTARGET structure describes the decode render target surface. 



## -syntax

````
typedef struct _D3DDDIARG_SETDECODERENDERTARGET {
  HANDLE hDecode;
  HANDLE hRenderTarget;
  UINT   SubResourceIndex;
} D3DDDIARG_SETDECODERENDERTARGET;
````


## -struct-fields

### -field hDecode

[in] A handle to the Microsoft DirectX Video Acceleration (DirectX VA) decode device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a> function.


### -field hRenderTarget

[in] A handle to the decode render target surface.


### -field SubResourceIndex

[in] An index into the resource for the decode render target surface.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdecoderendertarget.md">SetDecodeRenderTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETDECODERENDERTARGET structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

