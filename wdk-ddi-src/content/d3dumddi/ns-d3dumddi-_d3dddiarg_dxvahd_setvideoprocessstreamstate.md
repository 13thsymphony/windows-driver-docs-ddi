---
UID: NS.D3DUMDDI._D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
title: _D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure describes the stream state of the video processor to change and the data that is used to change the state.
old-location: display\d3dddiarg_dxvahd_setvideoprocessstreamstate.htm
old-project: display
ms.assetid: f1f99725-4110-49b4-9149-1f6d03faeb0e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE, D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
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

# _D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure



## -description
The D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure describes the stream state of the video processor to change and the data that is used to change the state. 



## -syntax

````
typedef struct _D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE {
  HANDLE                 hVideoProcessor;
  UINT                   StreamNumber;
  DXVAHDDDI_STREAM_STATE State;
  UINT                   DataSize;
  const VOID             *pData;
} D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE;
````


## -struct-fields

### -field hVideoProcessor

[in] A handle to the video processor whose stream state is changed.


### -field StreamNumber

[in] A zero-based stream index number. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure. 


### -field State

[in] A <a href="display.dxvahdddi_stream_state">DXVAHDDDI_STREAM_STATE</a>-typed value that indicates the stream state to modify.


### -field DataSize

[in] The size, in bytes, of the data that is used to change the stream state.


### -field pData

[in] A pointer to the data that is used to change the stream state. For more information about the types of data that <b>pData</b> can point to, see the values of the <a href="display.dxvahdddi_stream_state">DXVAHDDDI_STREAM_STATE</a> enumeration. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE is supported beginning with the Windows 7 operating system.

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
<a href="display.dxvahdddi_stream_state">DXVAHDDDI_STREAM_STATE</a>
</dt>
<dt>
<a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

