---
UID: NC.d3d10umddi.PFND3DWDDM2_2DDI_SET_SHADERCACHE_SESSION
title: PFND3DWDDM2_2DDI_SET_SHADERCACHE_SESSION
author: windows-driver-content
description: The pfnSetShaderCacheSession callback function sets a shader cache session.
old-location: display\pfnd3dwddm2_2ddi_set_shadercache_session.htm
old-project: display
ms.assetid: 18BA159D-5E78-41AC-8CB8-97AEC2AE9592
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnSetShaderCacheSession
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

# PFND3DWDDM2_2DDI_SET_SHADERCACHE_SESSION callback



## -description
The <i>pfnSetShaderCacheSession</i> callback function sets a shader cache session.



## -prototype

````
PFND3DWDDM2_2DDI_SET_SHADERCACHE_SESSION pfnSetShaderCacheSession;

VOID APIENTRY* pfnSetShaderCacheSession(
   D3D10DDI_HDEVICE            hDevice,
   D3DWDDM2_2DDI_HCACHESESSION hCacheSession
)
{ ... }
````


## -parameters

### -param hDevice 

The handle of a device.


### -param hCacheSession 

The handle of a cache session.


## -returns
This callback function does not return a value.


## -remarks
Access this callback function by using the <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs~r1.md">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs~r1.md">D3DWDDM2_2DDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_2DDI_SET_SHADERCACHE_SESSION callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

