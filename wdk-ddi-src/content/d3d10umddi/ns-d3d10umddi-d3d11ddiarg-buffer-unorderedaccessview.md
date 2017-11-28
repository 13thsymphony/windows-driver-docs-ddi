---
UID: NS.d3d10umddi.D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
title: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
author: windows-driver-content
description: The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_buffer_unorderedaccessview.htm
old-project: display
ms.assetid: a5ff1158-539f-4b25-8b65-72d077108c46
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW, D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
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

# D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure



## -description
<p>The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi-createunorderedaccessview.md">CreateUnorderedAccessView</a> function. </p>


## -syntax

````
typedef struct D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW {
  UINT FirstElement;
  UINT NumElements;
  UINT Flags;
} D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW;
````


## -struct-fields
<dl>

### -field <b>FirstElement</b>

<dd>
<p>[in] The offset, in bytes, to the first element in the buffer. </p>
</dd>

### -field <b>NumElements</b>

<dd>
<p>[in] The number of elements in the buffer. </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A valid bitwise OR of flag values that describe the buffer. The Direct3D runtime supports the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>
<dl>

### -field D3D11_DDI_BUFFER_UAV_FLAG_RAW 


### -field (0x00000001)

</dl>
</p>
</td>
<td>
<p>The buffer is in raw format.</p>
</td>
</tr>
<tr>
<td>
<p>
<dl>

### -field D3D11_DDI_BUFFER_UAV_FLAG_APPEND 


### -field (0x00000002)

</dl>
</p>
</td>
<td>
<p>Associate a counter with the UAV that has append semantics. The count reflects how many items are stored. However, the order in which the items are stored can change.</p>
</td>
</tr>
<tr>
<td>
<p>
<dl>

### -field D3D11_DDI_BUFFER_UAV_FLAG_COUNTER 


### -field (0x00000004)

</dl>
</p>
</td>
<td>
<p>Associate a counter with the UAV whose semantics prevent the reordering of the contents of the UAV. Therefore, applications can depend on the storage order. For example, applications can create linked lists by using count values to reference stored items.</p>
</td>
</tr>
</table>
<p> </p>
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
<p>D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system. </p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi-calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi-createunorderedaccessview.md">CreateUnorderedAccessView</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542086">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
