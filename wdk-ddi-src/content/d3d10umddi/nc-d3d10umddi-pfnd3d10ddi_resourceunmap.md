---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEUNMAP
title: PFND3D10DDI_RESOURCEUNMAP
author: windows-driver-content
description: The ResourceUnmap function unmaps a subresource of a resource.
old-location: display\resourceunmap.htm
old-project: display
ms.assetid: fb2b714e-232d-40b2-88ad-ee8dcd70a057
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D10DDI_RESOURCEUNMAP, ResourceUnmap, ResourceUnmap callback function [Display Devices], UserModeDisplayDriverDx10_Functions_473ebdfc-f365-4194-9d52-6338e19ca0d5.xml, d3d10umddi/ResourceUnmap, display.resourceunmap
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
-	ResourceUnmap
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_RESOURCEUNMAP callback function
The <i>ResourceUnmap</i> function unmaps a subresource of a resource.

## Syntax

```
PFND3D10DDI_RESOURCEUNMAP Pfnd3d10ddiResourceunmap;

void Pfnd3d10ddiResourceunmap(
   D3D10DDI_HDEVICE,
   D3D10DDI_HRESOURCE,
   UINT
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_HRESOURCE`



`UINT`




## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.

## Remarks

The driver can call <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> to set the <b>D3DDDIERR_DEVICEREMOVED</b> error code; however, the driver is not required to set <b>D3DDDIERR_DEVICEREMOVED</b> if the device was removed. Calls to <b>pfnSetErrorCb</b> to set any other error code are critical.

<h3><a id="Restrictions_on_input_values"></a><a id="restrictions_on_input_values"></a><a id="RESTRICTIONS_ON_INPUT_VALUES"></a>Restrictions on input values</h3>
For Windows Display Driver Model (WDDM) 1.3 and later drivers, the Microsoft Direct3D runtime supplies a restricted set of input values used by this function. For a list of all restricted values, see <a href="https://msdn.microsoft.com/F9AAE489-EC45-4EE6-875E-E084BB3054EE">Direct3D rendering performance improvements</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>