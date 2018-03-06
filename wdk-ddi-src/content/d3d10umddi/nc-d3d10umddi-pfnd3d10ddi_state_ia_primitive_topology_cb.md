---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB
title: PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB
author: windows-driver-content
description: The pfnStateIaPrimitiveTopologyCb function causes the Microsoft Direct3D 10 runtime to refresh the primitive topology state.
old-location: display\pfnstateiaprimitivetopologycb.htm
old-project: display
ms.assetid: 5a394a5b-afbc-41f5-8013-ab228e6284f9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB, d3d10state_functions_5866253f-2d14-41e3-b60d-d633b272848c.xml, d3d10umddi/pfnStateIaPrimitiveTopologyCb, display.pfnstateiaprimitivetopologycb, pfnStateIaPrimitiveTopologyCb, pfnStateIaPrimitiveTopologyCb callback function [Display Devices]
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
-	pfnStateIaPrimitiveTopologyCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB callback function
The <b>pfnStateIaPrimitiveTopologyCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the primitive topology state.

## Syntax

```
PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB Pfnd3d10ddiStateIaPrimitiveTopologyCb;

void Pfnd3d10ddiStateIaPrimitiveTopologyCb(
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
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>