---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_DS_SHADER_CB
title: PFND3D11DDI_STATE_DS_SHADER_CB
author: windows-driver-content
description: The pfnStateDsShaderCb function causes the Microsoft Direct3D 11 runtime to refresh the domain shader.
old-location: display\pfnstatedsshadercb.htm
old-project: display
ms.assetid: 3b50f462-667e-4772-89bb-32d01e1bb7fc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnstatedsshadercb, pfnStateDsShaderCb callback function [Display Devices], pfnStateDsShaderCb, PFND3D11DDI_STATE_DS_SHADER_CB, PFND3D11DDI_STATE_DS_SHADER_CB, d3d10umddi/pfnStateDsShaderCb, d3d11state_functions_5ab17831-b238-4b96-89bf-84c658463597.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateDsShaderCb is supported beginning with the Windows 7 operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	pfnStateDsShaderCb
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11DDI_STATE_DS_SHADER_CB callback function
The <b>pfnStateDsShaderCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the domain shader.

## Syntax

```
PFND3D11DDI_STATE_DS_SHADER_CB Pfnd3d11ddiStateDsShaderCb;

void Pfnd3d11ddiStateDsShaderCb(
   D3D10DDI_HRTCORELAYER
)
{...}
```

## Parameters

`D3D10DDI_HRTCORELAYER`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | pfnStateDsShaderCb is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_STATE_DS_SHADER_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>