---
UID: NE.d3dumddi._DXVAHDDDI_ALPHA_FILL_MODE
title: DXVAHDDDI_ALPHA_FILL_MODE
author: windows-driver-content
description: The DXVAHDDDI_ALPHA_FILL_MODE enumeration contains values that identify the type of alpha fill mode to set.
old-location: display\dxvahdddi_alpha_fill_mode.htm
old-project: display
ms.assetid: 6b0fdae8-d313-4281-bab0-b3dcc38b19e5
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_ALPHA_FILL_MODE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_ALPHA_FILL_MODE
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
req.iface: 
---

# DXVAHDDDI_ALPHA_FILL_MODE enumeration



## -description
<p>The DXVAHDDDI_ALPHA_FILL_MODE enumeration contains values that identify the type of alpha fill mode to set. </p>


## -syntax

````
typedef enum _DXVAHDDDI_ALPHA_FILL_MODE { 
  DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE         = 0,
  DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND     = 1,
  DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION    = 2,
  DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM  = 3
} DXVAHDDDI_ALPHA_FILL_MODE;
````


## -enum-fields
<dl>

### -field <a id="DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE"></a><a id="dxvahdddi_alpha_fill_mode_opaque"></a><b>DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE</b>

<dd>
<p>A value that specifies to fill the output with opaque alpha channel data. </p>
</dd>

### -field <a id="DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND"></a><a id="dxvahdddi_alpha_fill_mode_background"></a><b>DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND</b>

<dd>
<p>A value that specifies to fill the output with the alpha channel data of the background. For more information about background color, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff562993">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>. </p>
</dd>

### -field <a id="DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION"></a><a id="dxvahdddi_alpha_fill_mode_destination"></a><b>DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION</b>

<dd>
<p>A value that specifies to keep the alpha channel data unchanged on the target output. </p>
</dd>

### -field <a id="DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM"></a><a id="dxvahdddi_alpha_fill_mode_source_stream"></a><b>DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM</b>

<dd>
<p>A value that specifies to fill the output with the alpha channel data of the destination rectangle in which the source rectangle of the specified input stream is scaled. For more information about the conditions for this value, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562985">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_ALPHA_FILL_MODE is supported beginning with the Windows 7 operating system.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562985">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562993">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_ALPHA_FILL_MODE enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
