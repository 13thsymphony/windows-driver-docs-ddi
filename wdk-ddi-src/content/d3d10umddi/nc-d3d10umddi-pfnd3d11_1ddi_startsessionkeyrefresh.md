---
UID : NC:d3d10umddi.PFND3D11_1DDI_STARTSESSIONKEYREFRESH
title : PFND3D11_1DDI_STARTSESSIONKEYREFRESH
author : windows-driver-content
description : Gets a random number that can be used to refresh the session key.
old-location : display\startsessionkeyrefresh1.htm
old-project : display
ms.assetid : 0973cef3-41a8-495e-aa8a-ce64df53b892
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.startsessionkeyrefresh1, pfnStartSessionKeyRefresh callback function [Display Devices], pfnStartSessionKeyRefresh, PFND3D11_1DDI_STARTSESSIONKEYREFRESH, PFND3D11_1DDI_STARTSESSIONKEYREFRESH, d3d10umddi/pfnStartSessionKeyRefresh
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
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


# PFND3D11_1DDI_STARTSESSIONKEYREFRESH callback function
Gets a random number that can be used to refresh the session key.

## Syntax

```
PFND3D11_1DDI_STARTSESSIONKEYREFRESH Pfnd3d111DdiStartsessionkeyrefresh;

void Pfnd3d111DdiStartsessionkeyrefresh(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  UINT RandomNumberSize,
  VOID *pRandomNumber
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hCryptoSession`

A handle to the cryptographic session object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function.

`RandomNumberSize`

The size, in bytes, of the number in the buffer that is referenced by the <i>pRandomNumber</i> parameter.

`*pRandomNumber`




## Return Value

This callback function does not return a value.

## Remarks

The hardware and driver can optionally support <b>StartSessionKeyRefresh</b> for all cryptographic types.



When the Microsoft Direct3D runtime calls the driver's <b>StartSessionKeyRefresh</b> function, the driver generates and saves a random number and returns it in the buffer that the <i>pRandomNumber</i> parameter points to.

When the runtime subsequently calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function, the driver refreshes the session key by performing an XOR operation of the random number with the key.

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

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_STARTSESSIONKEYREFRESH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>