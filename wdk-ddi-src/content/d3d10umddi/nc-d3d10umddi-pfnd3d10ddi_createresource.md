---
UID: NC:d3d10umddi.PFND3D10DDI_CREATERESOURCE
title: PFND3D10DDI_CREATERESOURCE
author: windows-driver-content
description: Creates a resource.
old-location: display\createresource_d3d10_.htm
old-project: display
ms.assetid: c21839f0-8302-49f9-a2b4-4009fbd2d88c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateResource, CreateResource callback function [Display Devices], PFND3D10DDI_CREATERESOURCE, UserModeDisplayDriverDx10_Functions_8cad56f3-3374-45ac-8934-60802fea0764.xml, d3d10umddi/CreateResource, display.createresource_d3d10_
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
-	CreateResource
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CREATERESOURCE callback function
Creates a resource.

## Syntax

```
PFND3D10DDI_CREATERESOURCE Pfnd3d10ddiCreateresource;

void Pfnd3d10ddiCreateresource(
   D3D10DDI_HDEVICE,
  CONST D3D10DDIARG_CREATERESOURCE *,
   D3D10DDI_HRESOURCE,
   D3D10DDI_HRTRESOURCE
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`



`D3D10DDI_HRESOURCE`



`D3D10DDI_HRTRESOURCE`




## Return Value

None.

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see Remarks.

## Remarks

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The driver can also pass DXGI_DDI_ERR_UNSUPPORTED in a call to <b>pfnSetErrorCb</b>. For more information about passing DXGI_DDI_ERR_UNSUPPORTED, see the Remarks section of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> reference page. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/3ff77844-eeee-4fda-8798-2e240bc51379">DestroyResource(D3D10)</a> function to destroy the handle that the <i>hResource</i> parameter specifies.

The runtime will validate all parameters against the parameters that an application sent to create the resource. Therefore, the driver should not receive invalid combinations.

If the application does not require the contents of the resource to persist across presentations, the runtime will set the D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT flag of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542004">D3D10_DDI_RESOURCE_MISC_FLAG</a> enumeration in the <b>MiscFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> structure that the <i>pCreateResource</i> parameter points to. Presentation occurs when the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> (with the <b>Present</b> flag set in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557451">DXGI_DDI_ARG_BLT_FLAGS</a> structure) function is called. The runtime uses the D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT flag to create swap-chain back buffers when an application uses the DXGI_SWAP_EFFECT_DISCARD value to request swap chains.

<h3><a id="Creating_a_Stereo_Back_Buffer"></a><a id="creating_a_stereo_back_buffer"></a><a id="CREATING_A_STEREO_BACK_BUFFER"></a>Creating a Stereo Back Buffer</h3>
Beginning in Windows 8, if the driver must create a stereo back buffer, it should set members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> structure pointed to by <i>pCreateResource</i> as follows:

<ol>
<li>Set the <b>ArraySize</b> member to a value of 2.</li>
<li>Set the D3D10_DDI_BIND_PRESENT flag value in the <b>BindFlags</b> member.</li>
</ol>
Additionally, to support stereo presentation, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> function must allow any values for the <b>DstSubresource</b> and <b>SrcSubresource</b> members of  the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557447">DXGI_DDI_ARG_BLT</a> structure that are within the range of the source and destination resources.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a>



<a href="https://msdn.microsoft.com/2c4eb002-4788-46ab-92b9-3bb2dcb44ee3">CalcPrivateResourceSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557447">DXGI_DDI_ARG_BLT</a>



<a href="https://msdn.microsoft.com/3ff77844-eeee-4fda-8798-2e240bc51379">DestroyResource(D3D10)</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>