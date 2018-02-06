---
UID: NC:d3d10umddi.PFND3D11DDI_DESTROYCOMMANDLIST
title: PFND3D11DDI_DESTROYCOMMANDLIST
author: windows-driver-content
description: The DestroyCommandList function destroys a command list.
old-location: display\destroycommandlist.htm
old-project: display
ms.assetid: 9f03c193-f017-4189-a082-908e28a2e9f7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroycommandlist, DestroyCommandList callback function [Display Devices], DestroyCommandList, PFND3D11DDI_DESTROYCOMMANDLIST, PFND3D11DDI_DESTROYCOMMANDLIST, d3d10umddi/DestroyCommandList, UserModeDisplayDriverDx11_Functions_cf01bd33-1921-4d56-a377-f8eda35a8d04.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyCommandList is supported beginning with the Windows 7 operating system.
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
-	DestroyCommandList
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11DDI_DESTROYCOMMANDLIST callback function
The <b>DestroyCommandList</b> function destroys a command list.

## Syntax

```
PFND3D11DDI_DESTROYCOMMANDLIST Pfnd3d11ddiDestroycommandlist;

void Pfnd3d11ddiDestroycommandlist(
   D3D10DDI_HDEVICE,
   D3D11DDI_HCOMMANDLIST
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11DDI_HCOMMANDLIST`




## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

The driver is only required to implement <b>DestroyCommandList</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DestroyCommandList</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The driver can implement a <b>DestroyCommandList</b> function that contains a <b>switch</b> statement to process the destruction of command lists and the lightweight destruction of command lists. That is, the driver can implement one <b>DestroyCommandList</b>, and can set the <b>pfnRecycleDestroyCommandList</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a> structure to point to <b>DestroyCommandList</b> along with the <b>pfnRecycleDestroyCommandList</b> member of D3D11DDI_DEVICEFUNCS to point to <b>DestroyCommandList</b>. However, to improve performance, the driver can implement separate <b>DestroyCommandList</b> and <b>RecycleDestroyCommandList</b> functions.

For more information about <b>RecycleDestroyCommandList</b>, see <a href="https://msdn.microsoft.com/7bede247-680d-4fd3-a10b-6ef63f0a88ec">Optimization for Small Command Lists</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DestroyCommandList is supported beginning with the Windows 7 operating system. DestroyCommandList is supported beginning with the Windows 7 operating system. |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcommandlist.md">CreateCommandList</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_DESTROYCOMMANDLIST callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>