---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_PS_SAMPLER_CB
title: PFND3D10DDI_STATE_PS_SAMPLER_CB
author: windows-driver-content
description: The pfnStatePsSamplerCb function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound samplers.
old-location: display\pfnstatepssamplercb.htm
old-project: display
ms.assetid: 8cf25918-1acf-40b6-be51-2c1afc419f2a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D10DDI_STATE_PS_SAMPLER_CB, d3d10state_functions_2e14a132-dd8b-4a78-905e-b2d74d9e669d.xml, d3d10umddi/pfnStatePsSamplerCb, display.pfnstatepssamplercb, pfnStatePsSamplerCb, pfnStatePsSamplerCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	pfnStatePsSamplerCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_STATE_PS_SAMPLER_CB callback function
The <b>pfnStatePsSamplerCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound samplers.

## Syntax

```
PFND3D10DDI_STATE_PS_SAMPLER_CB Pfnd3d10ddiStatePsSamplerCb;

void Pfnd3d10ddiStatePsSamplerCb(
   D3D10DDI_HRTCORELAYER,
   UINT,
   UINT
)
{...}
```

## Parameters

`D3D10DDI_HRTCORELAYER`



`UINT`



`UINT`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_PS_SAMPLER_CB callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>