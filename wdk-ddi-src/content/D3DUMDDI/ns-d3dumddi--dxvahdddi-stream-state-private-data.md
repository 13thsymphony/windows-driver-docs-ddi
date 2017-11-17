---
UID: NS.d3dumddi._DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
title: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure describes stream-state data that specifies a private stream state.
old-location: display\dxvahdddi_stream_state_private_data.htm
ms.assetid: 1352392f-62d4-46aa-aa59-651309c36e6f
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
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
ms.keywords: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA, DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
req.iface: 
---

# DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure



## -description
<p>The DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure describes stream-state data that specifies a private stream state. </p>


## -syntax

````
typedef struct _DXVAHDDDI_STREAM_STATE_PRIVATE_DATA {
  GUID Guid;
  UINT DataSize;
  VOID *pData;
} DXVAHDDDI_STREAM_STATE_PRIVATE_DATA;
````


## -struct-fields
<dl>

### -field <b>Guid</b>

<dd>
<p>[in] A GUID that identifies the private stream state.  </p>
</dd>

### -field <b>DataSize</b>

<dd>
<p>[in] The size, in bytes, of the private stream-state data. </p>
</dd>

### -field <b>pData</b>

<dd>
<p>[in/out] A pointer to the private stream-state data. The caller sets <b>pData</b> to <b>NULL</b> to retrieve the size of the private stream-state data. </p>
</dd>
</dl>

## -remarks
<p>Unlike other stream states (<a href="https://msdn.microsoft.com/library/windows/hardware/ff563068">DXVAHDDDI_STREAM_STATE</a>), the Direct3D runtime does not maintain the private stream state. An application and the driver communicates the private stream state directly through a proprietary manner, which consists of setting and retrieving the private stream state. </p>

<p>To set private stream state, the application causes the Direct3D runtime to specify the DXVAHDDDI_STREAM_STATE_PRIVATE state in the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543098">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a> function. To retrieve private stream state, the application causes the Direct3D runtime to call the driver's <a href="https://msdn.microsoft.com/0503b382-8ed3-461e-906f-27953ac5f757">GetVideoProcessStreamStatePrivate</a> function. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_STREAM_STATE_PRIVATE_DATA is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543098">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563068">DXVAHDDDI_STREAM_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/0503b382-8ed3-461e-906f-27953ac5f757">GetVideoProcessStreamStatePrivate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
