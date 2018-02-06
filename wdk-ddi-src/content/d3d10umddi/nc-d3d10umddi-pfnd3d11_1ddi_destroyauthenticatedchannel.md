---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL
author: windows-driver-content
description: Releases resources for the authenticated channel that were created through a call to the CreateAuthenticatedChannel(D3D11_1) function.
old-location: display\destroyauthenticatedchannel1.htm
old-project: display
ms.assetid: 3eebda5e-72c6-4167-a886-58e877551923
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroyauthenticatedchannel1, pfnDestroyAuthenticatedChannel callback function [Display Devices], pfnDestroyAuthenticatedChannel, PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL, PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL, d3d10umddi/pfnDestroyAuthenticatedChannel, display.pfndestroyauthenticatedchannel1
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnDestroyAuthenticatedChannel
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL callback function
Releases resources for the authenticated channel that were created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.

## Syntax

```
PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL Pfnd3d111DdiDestroyauthenticatedchannel;

void Pfnd3d111DdiDestroyauthenticatedchannel(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HAUTHCHANNEL hAuthChannel
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hAuthChannel`

A handle to the driver's private data for the authenticated channel. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>