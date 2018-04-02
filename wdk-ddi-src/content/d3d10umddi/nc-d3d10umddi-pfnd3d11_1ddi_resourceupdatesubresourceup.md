---
UID: NC:d3d10umddi.PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP
title: PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP
author: windows-driver-content
description: Updates a destination subresource region that stores constant buffers from a source system-memory region. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\defaultconstantbufferupdatesubresourceup_d3d11_1_.htm
old-project: display
ms.assetid: 67FCC9A4-B3C5-46FC-83ED-CFFB8186328F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DefaultConstantBufferUpdateSubresourceUP(D3D11_1), DefaultConstantBufferUpdateSubresourceUP(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP, d3d10umddi/DefaultConstantBufferUpdateSubresourceUP(D3D11_1), display.defaultconstantbufferupdatesubresourceup_d3d11_1_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	DefaultConstantBufferUpdateSubresourceUP(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP callback function
updates a destination subresource region that stores constant buffers from a source system-memory region. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## Syntax

```
PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP Pfnd3d111DdiResourceupdatesubresourceup;

void Pfnd3d111DdiResourceupdatesubresourceup(
   D3D10DDI_HDEVICE,
   D3D10DDI_HRESOURCE,
   UINT,
  CONST D3D10_DDI_BOX *,
  CONST VOID *,
   UINT,
   UINT,
  UINT CopyFlags
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_HRESOURCE`



`UINT`



`*`



`*`



`UINT`



`UINT`



`CopyFlags`

A value that specifies characteristics of copy operation as a bitwise <b>OR</b> of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451047">D3D11_1_DDI_COPY_FLAGS</a> enumeration type.


## Return Value

None.

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <b>DefaultConstantBufferUpdateSubresourceUP(D3D11_1)</b> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451047">D3D11_1_DDI_COPY_FLAGS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>