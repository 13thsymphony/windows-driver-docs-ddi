---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
title: _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure describes the private stream-state of the video processor to retrieve.
old-location: display\d3dddiarg_dxvahd_getvideoprocessstreamstateprivate.htm
old-project: display
ms.assetid: f55dc37a-fb67-48fe-8e32-29b2e71b6abc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
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
req.typenames: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
---

# _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure



## -description
The D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure describes the private stream-state of the video processor to retrieve. 



## -syntax

````
typedef struct _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE {
  HANDLE                              hVideoProcessor;
  UINT                                StreamNumber;
  DXVAHDDDI_STREAM_STATE_PRIVATE_DATA *pData;
} D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE;
````


## -struct-fields

### -field hVideoProcessor

[in] A handle to the video processor whose private stream-state is the runtime requests.


### -field StreamNumber

[in] A zero-based stream index number. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a> structure. 


### -field pData

[in/out] A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_private_data.md">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure that identifies the private stream state to retrieve. The driver uses DXVAHDDDI_STREAM_STATE_PRIVATE_DATA to return the private stream-state data. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE is supported beginning with the Windows 7 operating system.

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
<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_private_data.md">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate.md">GetVideoProcessStreamStatePrivate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

