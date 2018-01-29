---
UID : NC:d3d10umddi.PFND3D11DDI_STATE_DS_CONSTBUF_CB
title : PFND3D11DDI_STATE_DS_CONSTBUF_CB
author : windows-driver-content
description : The pfnStateDsConstBufCb function causes the Microsoft Direct3D 11 runtime to refresh the domain shader constant buffer state.
old-location : display\pfnstatedsconstbufcb.htm
old-project : display
ms.assetid : 8170be69-3e75-4e33-a123-3039e3f9d0c0
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.pfnstatedsconstbufcb, pfnStateDsConstBufCb callback function [Display Devices], pfnStateDsConstBufCb, PFND3D11DDI_STATE_DS_CONSTBUF_CB, PFND3D11DDI_STATE_DS_CONSTBUF_CB, d3d10umddi/pfnStateDsConstBufCb, d3d11state_functions_5672a801-6215-48f3-b107-82281c9e8a9d.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : pfnStateDsConstBufCb is supported beginning with the Windows 7 operating system.
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


# PFND3D11DDI_STATE_DS_CONSTBUF_CB callback function
The <b>pfnStateDsConstBufCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the domain shader constant buffer state.

## Syntax

```
PFND3D11DDI_STATE_DS_CONSTBUF_CB Pfnd3d11ddiStateDsConstbufCb;

void Pfnd3d11ddiStateDsConstbufCb(
   D3D10DDI_HRTCORELAYER,
   UINT,
   UINT
)
{...}
```

## Parameters

`D3D10DDI_HRTCORELAYER`



`UINT`



`UINT`




## Return Value

None


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

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_STATE_DS_CONSTBUF_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>