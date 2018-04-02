---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYEND
title: PFND3D10DDI_QUERYEND
author: windows-driver-content
description: The QueryEnd function marks the end of a sequence of graphics commands for a query and transitions the query to the &#0034;issued&#0034; state.
old-location: display\queryend.htm
old-project: display
ms.assetid: 5a231d7e-7e47-40ad-99d1-82661dec41d0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D10DDI_QUERYEND, QueryEnd, QueryEnd callback function [Display Devices], UserModeDisplayDriverDx10_Functions_9897bbe4-a58c-430b-815a-eb4360ce8043.xml, d3d10umddi/QueryEnd, display.queryend
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
-	QueryEnd
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_QUERYEND callback function
The <i>QueryEnd</i> function marks the end of a sequence of graphics commands for a query and transitions the query to the "issued" state.

## Syntax

```
PFND3D10DDI_QUERYEND Pfnd3d10ddiQueryend;

void Pfnd3d10ddiQueryend(
   D3D10DDI_HDEVICE,
   D3D10DDI_HQUERY
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_HQUERY`




## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

If the driver supports the <a href="https://msdn.microsoft.com/2f0a7462-83a6-47df-b5f6-b3706b875349">QueryBegin</a> function for a query operation, and if the Microsoft Direct3D runtime calls <i>QueryEnd</i> without call <i>QueryBegin</i>, the call is equivalent to first calling <i>QueryBegin</i> and then calling <i>QueryEnd</i> immediately afterward. In addition, the runtime cannot call <i>QueryEnd</i> on a predicate that is currently bound to the pipeline through a call to the <a href="https://msdn.microsoft.com/df671478-859f-4ccd-9ab4-1986f9af10cf">SetPredication</a> function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>QueryEnd</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/2f0a7462-83a6-47df-b5f6-b3706b875349">QueryBegin</a>



<a href="https://msdn.microsoft.com/df671478-859f-4ccd-9ab4-1986f9af10cf">SetPredication</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>