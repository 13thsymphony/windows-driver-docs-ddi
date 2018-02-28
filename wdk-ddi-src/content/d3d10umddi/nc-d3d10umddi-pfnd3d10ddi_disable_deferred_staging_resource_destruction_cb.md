---
UID: NC:d3d10umddi.PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB
title: PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB
author: windows-driver-content
description: The pfnDisableDeferredStagingResourceDestruction function disables the deferred destruction of staging resources.
old-location: display\pfndisabledeferredstagingresourcedestruction.htm
old-project: display
ms.assetid: f0328782-9b5b-44e6-ac58-7eb72685aa52
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB, d3d10state_functions_2a17cecf-fe42-4058-85d8-524e4ef4d207.xml, d3d10umddi/pfnDisableDeferredStagingResourceDestruction, display.pfndisabledeferredstagingresourcedestruction, pfnDisableDeferredStagingResourceDestruction, pfnDisableDeferredStagingResourceDestruction callback function [Display Devices]
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
-	pfnDisableDeferredStagingResourceDestruction
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB callback function
The <b>pfnDisableDeferredStagingResourceDestruction</b> function disables the deferred destruction of staging resources.

## Syntax

```
PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB Pfnd3d10ddiDisableDeferredStagingResourceDestructionCb;

void Pfnd3d10ddiDisableDeferredStagingResourceDestructionCb(
   D3D10DDI_HRTCORELAYER
)
{...}
```

## Parameters

`D3D10DDI_HRTCORELAYER`




## Return Value

None

## Remarks

By default, the Direct3D runtime defers the destruction of staging resources, until a call to the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy.md">ResourceIsStagingBusy</a> function indicates that the graphics pipeline no longer uses the resources. The runtime defers the destruction of staging resources because the destruction of a staging resource, while still in use, might cause the processor to block until the resource is no longer used. 

If the user-mode display driver can ensure that this type of block can be avoided, the driver can call <b>pfnDisableDeferredStagingResourceDestruction</b> to disable the deferred destruction behavior.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy.md">ResourceIsStagingBusy</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>