---
UID: NS.D3DUMDDI._D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
title: _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure describes the private bit-block transfer (bitblt) state of the video processor to retrieve.
old-location: display\d3dddiarg_dxvahd_getvideoprocessbltstateprivate.htm
old-project: display
ms.assetid: 0b6c0033-d6aa-4662-8818-ea737cf5a1c0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE, D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
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

# _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure



## -description
The D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure describes the private bit-block transfer (bitblt) state of the video processor to retrieve. 


## -syntax

````
typedef struct _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE {
  HANDLE                           hVideoProcessor;
  DXVAHDDDI_BLT_STATE_PRIVATE_DATA *pData;
} D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE;
````


## -struct-fields

### -field hVideoProcessor

[in] A handle to the video processor whose private bitblt state the runtime requests.

### -field pData

[in/out] A pointer to <a href="display.dxvahdddi_blt_state_private_data">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a> structure that identifies the private bitblt state to retrieve. The driver uses DXVAHDDDI_BLT_STATE_PRIVATE_DATA to return the private bitblt data. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE is supported beginning with the Windows 7 operating system.
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
<a href="display.dxvahdddi_blt_state_private_data">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessbltstateprivate.md">GetVideoProcessBltStatePrivate</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
