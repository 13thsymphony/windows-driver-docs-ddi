---
UID: NC:d3d10umddi.PFND3D10DDI_SETCONSTANTBUFFERS
title: PFND3D10DDI_SETCONSTANTBUFFERS
author: windows-driver-content
description: The CsSetConstantBuffers function sets constant buffers for a compute shader.
old-location: display\cssetconstantbuffers.htm
old-project: display
ms.assetid: 159ee0ac-7ddf-4ffd-a07f-3d58130b90e8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.cssetconstantbuffers, CsSetConstantBuffers callback function [Display Devices], CsSetConstantBuffers, PFND3D10DDI_SETCONSTANTBUFFERS, PFND3D10DDI_SETCONSTANTBUFFERS, d3d10umddi/CsSetConstantBuffers, UserModeDisplayDriverDx11_Functions_ae0b7e35-f8c5-428d-97d0-e22d5b609c72.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetConstantBuffers is supported beginning with the Windows 7 operating system.
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
-	CsSetConstantBuffers
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_SETCONSTANTBUFFERS callback function
The <b>CsSetConstantBuffers</b> function sets constant buffers for a compute shader.

## Syntax

```
PFND3D10DDI_SETCONSTANTBUFFERS Pfnd3d10ddiSetconstantbuffers;

void Pfnd3d10ddiSetconstantbuffers(
   D3D10DDI_HDEVICE,
  UINT StartSlot,
  UINT NumBuffers,
  CONST D3D10DDI_HRESOURCE *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`StartSlot`



`NumBuffers`

The total number of buffers to set.

`*`




## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

Buffers that the <b>CsSetConstantBuffers</b> function specifies are created with the D3D10_BIND_CONSTANT_BUFFER flag. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>CsSetConstantBuffers</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | CsSetConstantBuffers is supported beginning with the Windows 7 operating system. CsSetConstantBuffers is supported beginning with the Windows 7 operating system. |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SETCONSTANTBUFFERS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>