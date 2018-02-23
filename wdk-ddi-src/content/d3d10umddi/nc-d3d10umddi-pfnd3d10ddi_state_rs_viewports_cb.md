---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_RS_VIEWPORTS_CB
title: PFND3D10DDI_STATE_RS_VIEWPORTS_CB
author: windows-driver-content
description: The pfnStateRsViewportsCb function causes the Microsoft Direct3D 10 runtime to refresh the viewport state.
old-location: display\pfnstatersviewportscb.htm
old-project: display
ms.assetid: 9390ddca-4658-4853-a45c-9fb306bbdef8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnstatersviewportscb, pfnStateRsViewportsCb callback function [Display Devices], pfnStateRsViewportsCb, PFND3D10DDI_STATE_RS_VIEWPORTS_CB, PFND3D10DDI_STATE_RS_VIEWPORTS_CB, d3d10umddi/pfnStateRsViewportsCb, d3d10state_functions_ed84e257-d988-47db-a588-800a7c74ed45.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	pfnStateRsViewportsCb
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D10DDI_STATE_RS_VIEWPORTS_CB callback function
The <b>pfnStateRsViewportsCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the viewport state.

## Syntax

```
PFND3D10DDI_STATE_RS_VIEWPORTS_CB Pfnd3d10ddiStateRsViewportsCb;

void Pfnd3d10ddiStateRsViewportsCb(
   D3D10DDI_HRTCORELAYER
)
{...}
```

## Parameters

`D3D10DDI_HRTCORELAYER`




## Return Value

None

## Remarks

The <b>pfnStateRsViewportsCb</b> function calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setviewports.md">SetViewports</a> function with all of the currently set viewports.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setviewports.md">SetViewports</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_RS_VIEWPORTS_CB callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>