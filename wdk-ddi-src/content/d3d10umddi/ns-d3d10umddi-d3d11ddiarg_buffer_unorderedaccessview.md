---
UID: NS.D3D10UMDDI.D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
title: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
author: windows-driver-content
description: The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_buffer_unorderedaccessview.htm
old-project: display
ms.assetid: a5ff1158-539f-4b25-8b65-72d077108c46
ms.author: windowsdriverdev
ms.date: 12/15/2017
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
---

# D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure



## -description
The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a> function. 



## -syntax

````
typedef struct D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW {
  UINT FirstElement;
  UINT NumElements;
  UINT Flags;
} D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW;
````


## -struct-fields

### -field FirstElement

[in] The offset, in bytes, to the first element in the buffer. 


### -field NumElements

[in] The number of elements in the buffer. 


### -field Flags

[in] A valid bitwise OR of flag values that describe the buffer. The Direct3D runtime supports the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>


### -field D3D11_DDI_BUFFER_UAV_FLAG_RAW 
### -field (0x00000001)



</td>
<td>
The buffer is in raw format.

</td>
</tr>
<tr>
<td>


### -field D3D11_DDI_BUFFER_UAV_FLAG_APPEND 
### -field (0x00000002)



</td>
<td>
Associate a counter with the UAV that has append semantics. The count reflects how many items are stored. However, the order in which the items are stored can change.

</td>
</tr>
<tr>
<td>


### -field D3D11_DDI_BUFFER_UAV_FLAG_COUNTER 
### -field (0x00000004)



</td>
<td>
Associate a counter with the UAV whose semantics prevent the reordering of the contents of the UAV. Therefore, applications can depend on the storage order. For example, applications can create linked lists by using count values to reference stored items.

</td>
</tr>
</table>
 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system. 

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview.md">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

