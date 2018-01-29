---
UID : NC:d3d10umddi.PFND3D10_1DDI_RELOCATEDEVICEFUNCS
title : PFND3D10_1DDI_RELOCATEDEVICEFUNCS
author : windows-driver-content
description : The RelocateDeviceFuncs(D3D10_1) function notifies the user-mode display driver about the new location of the driver function table.
old-location : display\relocatedevicefuncs_d3d10_1_.htm
old-project : display
ms.assetid : 0141badb-0d2d-433f-950f-bf169087c574
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.relocatedevicefuncs_d3d10_1_, RelocateDeviceFuncs_D3D10_1 callback function [Display Devices], RelocateDeviceFuncs_D3D10_1, PFND3D10_1DDI_RELOCATEDEVICEFUNCS, PFND3D10_1DDI_RELOCATEDEVICEFUNCS, d3d10umddi/RelocateDeviceFuncs_D3D10_1, UserModeDisplayDriverDx10_Functions_5798bcfe-7d15-407d-b7c2-cfe907e94991.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : RelocateDeviceFuncs(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D10_1DDI_RELOCATEDEVICEFUNCS callback function
The <i>RelocateDeviceFuncs(D3D10_1)</i> function notifies the user-mode display driver about the new location of the driver function table.

## Syntax

```
PFND3D10_1DDI_RELOCATEDEVICEFUNCS Pfnd3d101DdiRelocatedevicefuncs;

void Pfnd3d101DdiRelocatedevicefuncs(
   D3D10DDI_HDEVICE,
  D3D10_1DDI_DEVICEFUNCS *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code.

## Remarks

A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D10_1)</i> function to replace function pointers in the driver function table.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_1DDI_RELOCATEDEVICEFUNCS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>