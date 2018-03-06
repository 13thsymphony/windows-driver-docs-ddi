---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION
title: PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION
author: windows-driver-content
description: The pfnDestroyShaderCacheSession callback function destroys a shader cache session.
old-location: display\pfnd3dwddm2_2ddi_destroy_shadercache_session.htm
old-project: display
ms.assetid: 1C6AFC89-F740-4309-9389-BFB5C62FCA77
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION, d3d10umddi/pfnDestroyShaderCacheSession, display.pfnd3dwddm2_2ddi_destroy_shadercache_session, pfnDestroyShaderCacheSession, pfnDestroyShaderCacheSession callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	pfnDestroyShaderCacheSession
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION callback function
The <i>pfnDestroyShaderCacheSession</i> callback function destroys a shader cache session.

## Syntax

```
PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION Pfnd3dwddm22DdiDestroyShadercacheSession;

void Pfnd3dwddm22DdiDestroyShadercacheSession(
   D3D10DDI_HDEVICE,
   D3DWDDM2_2DDI_HCACHESESSION
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3DWDDM2_2DDI_HCACHESESSION`




## Return Value

This callback function does not return a value.

## Remarks

Access this callback function by using the <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d10umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md">D3DWDDM2_2DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>