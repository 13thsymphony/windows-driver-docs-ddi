---
UID: NC:d3d10umddi.PFND3D10DDI_SETPREDICATION
title: PFND3D10DDI_SETPREDICATION
author: windows-driver-content
description: The SetPredication function specifies whether rendering and resource-manipulation commands that follow are actually performed.
old-location: display\setpredication.htm
old-project: display
ms.assetid: df671478-859f-4ccd-9ab4-1986f9af10cf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_SETPREDICATION, SetPredication, SetPredication callback function [Display Devices], UserModeDisplayDriverDx10_Functions_358db7d9-6533-4c37-b761-985c921f4957.xml, d3d10umddi/SetPredication, display.setpredication
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
-	SetPredication
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_SETPREDICATION callback function
The <i>SetPredication</i> function specifies whether rendering and resource-manipulation commands that follow are actually performed.

## Syntax

```
PFND3D10DDI_SETPREDICATION Pfnd3d10ddiSetpredication;

void Pfnd3d10ddiSetpredication(
   D3D10DDI_HDEVICE,
   D3D10DDI_HQUERY,
   BOOL
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_HQUERY`



`BOOL`




## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

Some predicates are only hints; therefore, they might not actually prevent operations from being performed. The Microsoft Direct3D runtime primarily calls <i>SetPredication</i> to let applications issue graphics commands without taking the performance hit of spinning and waiting for a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function to return. Therefore, predication can occur even if <i>QueryGetData</i> returns S_FALSE. In other words, an application can also use predication as a fallback if <i>QueryGetData</i> possibly returns S_FALSE. If <i>QueryGetData</i> returns S_OK, the application can skip calling the graphics commands manually with its own application logic.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetPredication</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SETPREDICATION callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>