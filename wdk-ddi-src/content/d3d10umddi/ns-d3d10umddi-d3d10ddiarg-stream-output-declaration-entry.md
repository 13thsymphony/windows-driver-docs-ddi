---
UID: NS.d3d10umddi.D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
title: D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
author: windows-driver-content
description: The D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure describes a portion of the stream output for a geometry shader.
old-location: display\d3d10ddiarg_stream_output_declaration_entry.htm
old-project: display
ms.assetid: 42d01b63-ca3b-4348-bf50-a1d648548266
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY, D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
req.alt-loc: d3d10umddi.h
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

# D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure



## -description
<p>The D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure describes a portion of the stream output for a geometry shader.</p>


## -syntax

````
typedef struct D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY {
  UINT OutputSlot;
  UINT RegisterIndex;
  BYTE RegisterMask;
} D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY;
````


## -struct-fields
<dl>

### -field <b>OutputSlot</b>

<dd>
<p>[in] The number of the slot for the portion of the stream output. </p>
</dd>

### -field <b>RegisterIndex</b>

<dd>
<p>[in] The number of the register for the portion of the stream output.</p>
</dd>

### -field <b>RegisterMask</b>

<dd>
<p>[in] The xyzw register mask for the portion of the stream output. That is, the four least signifigant bits (LSBs) of the mask represent xyzw respectively. </p>
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
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-creategeometryshaderwithstreamoutput.md">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
