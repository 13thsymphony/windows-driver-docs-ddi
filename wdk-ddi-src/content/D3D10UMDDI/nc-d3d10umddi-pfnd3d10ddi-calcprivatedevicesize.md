---
UID: NC.d3d10umddi.PFND3D10DDI_CALCPRIVATEDEVICESIZE
title: PFND3D10DDI_CALCPRIVATEDEVICESIZE
author: windows-driver-content
description: The CalcPrivateDeviceSize function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.
old-location: display\calcprivatedevicesize.htm
ms.assetid: 8221a99a-1b46-48ba-8930-ac973e009eee
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CalcPrivateDeviceSize
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
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
req.iface: 
---

# PFND3D10DDI_CALCPRIVATEDEVICESIZE callback



## -description
<p>The <b>CalcPrivateDeviceSize</b> function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data. </p>


## -prototype

````
PFND3D10DDI_CALCPRIVATEDEVICESIZE CalcPrivateDeviceSize;

SIZE_T APIENTRY CalcPrivateDeviceSize(
  _In_       D3D10DDI_HADAPTER                 hAdapter,
  _In_ const D3D10DDIARG_CALCPRIVATEDEVICESIZE *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>hAdapter</i> [in]

<dd>
<p> A handle that identifies the graphics adapter. </p>
</dd>

### -param <i>pData</i> [in]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541649">D3D10DDIARG_CALCPRIVATEDEVICESIZE</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.</p>
</dd>
</dl>

## -returns
<p><b>CalcPrivateDeviceSize</b> returns the size of the memory region that the driver requires to store frequently-accessed data.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541649">D3D10DDIARG_CALCPRIVATEDEVICESIZE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATEDEVICESIZE callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
