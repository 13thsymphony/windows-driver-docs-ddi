---
UID: NC:d3d10umddi.PFND3D11DDI_DISPATCHINDIRECT
title: PFND3D11DDI_DISPATCHINDIRECT
author: windows-driver-content
description: The DispatchIndirect function executes the compute shader.
old-location: display\dispatchindirect.htm
old-project: display
ms.assetid: 0c818515-163f-48ba-ad57-f4405672c98f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DispatchIndirect, DispatchIndirect callback function [Display Devices], PFND3D11DDI_DISPATCHINDIRECT, UserModeDisplayDriverDx11_Functions_39c7b613-66de-4dd8-8b43-d1ae2a926e77.xml, d3d10umddi/DispatchIndirect, display.dispatchindirect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DispatchIndirect is supported beginning with the Windows 7 operating system.
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
-	DispatchIndirect
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11DDI_DISPATCHINDIRECT callback function
The <b>DispatchIndirect</b> function executes the compute shader.

## Syntax

```
PFND3D11DDI_DISPATCHINDIRECT Pfnd3d11ddiDispatchindirect;

void Pfnd3d11ddiDispatchindirect(
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

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

The DispatchIndirect function performs the same task as the call to the driver's <a href="https://msdn.microsoft.com/6fbbf05a-efb0-4f24-8811-b87141cf2daa">Dispatch</a> function. The Direct3D runtime calls the driver's <b>DispatchIndirect</b> function on the display device to execute the compute shader over a number of threads in a grid of thread groups. However, <b>DispatchIndirect</b> obtains the number of thread groups to execute from the contents of the buffer that the <i>hBufferForArgs</i> parameter specifies.  <b>DispatchIndirect</b> reads three UINT values, starting at the byte offset that the <i>AlignedByteOffsetForArgs</i> parameter specifies.

When the Direct3D runtime calls the driver's <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function to create the buffer resource that the <i>hBufferForArgs</i> parameter specifies, the runtime must set the D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS flag in the <b>MiscFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> structure.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DispatchIndirect</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DispatchIndirect is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/6fbbf05a-efb0-4f24-8811-b87141cf2daa">Dispatch</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>