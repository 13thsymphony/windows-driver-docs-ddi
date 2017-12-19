---
UID: NS.D3D10UMDDI.D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
title: D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location: display\d3d10ddiarg_buffer_shaderresourceview.htm
old-project: display
ms.assetid: 9144b167-7fa4-4854-bf0c-e98192f07db8
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW, D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
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
req.alt-api: D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
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

# D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure



## -description
The D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a> function. 



## -syntax

````
typedef struct D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW {
  union {
    UINT FirstElement;
    UINT ElementOffset;
  };
  union {
    UINT NumElements;
    UINT ElementWidth;
  };
} D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW;
````


## -struct-fields

### -field FirstElement


### -field ElementOffset

[in] The offset (that is, the number of elements) between the beginning of the buffer and the first element that is to be used in the view, starting at 0. 


### -field NumElements


### -field ElementWidth

[in] The number of elements in the view. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

