---
UID: NC:d3d10umddi.PFND3D10DDI_SETTEXTFILTERSIZE
title: PFND3D10DDI_SETTEXTFILTERSIZE
author: windows-driver-content
description: The SetTextFilterSize function sets the width and height of the monochrome convolution filter.
old-location: display\settextfiltersize.htm
old-project: display
ms.assetid: 663fd3c3-7a8f-446d-b45a-392716116407
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D10DDI_SETTEXTFILTERSIZE, SetTextFilterSize, SetTextFilterSize callback function [Display Devices], UserModeDisplayDriverDx10_Functions_418992fe-bd22-446c-94a2-2a4d23fd63a7.xml, d3d10umddi/SetTextFilterSize, display.settextfiltersize
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
-	SetTextFilterSize
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_SETTEXTFILTERSIZE callback function
The <i>SetTextFilterSize</i> function sets the width and height of the monochrome convolution filter.

## Syntax

```
PFND3D10DDI_SETTEXTFILTERSIZE Pfnd3d10ddiSettextfiltersize;

void Pfnd3d10ddiSettextfiltersize(
   D3D10DDI_HDEVICE,
   UINT,
   UINT
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`UINT`



`UINT`




## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

The number of samples that are required from a kernel's dimensions is actually (<i>Width</i> + 1) x (<i>Height</i> + 1), which can come out to from 4 to 64 samples. These settings apply across all samplers that are configured to use the D3D10_DDI_FILTER_TEXT_1BIT filter from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541952">D3D10_DDI_FILTER</a> enumeration.

<i>SetTextFilterSize</i> ensures that values that are supplied in the <i>Width</i> and <i>Height</i> parameters are in range. The default vaules for <i>Width</i> and <i>Height</i> are both 1, initially. The driver must set these default values during device creation.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED. However, if device removal interfered with the operation of <i>SetTextFilterSize</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541952">D3D10_DDI_FILTER</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>