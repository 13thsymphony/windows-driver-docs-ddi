---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKCOUNTER
title: PFND3D10DDI_CHECKCOUNTER
author: windows-driver-content
description: The CheckCounter function retrieves information that describes a counter.
old-location: display\checkcounter.htm
old-project: display
ms.assetid: 592a5146-a2fe-41d1-854b-df27a97bd513
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.checkcounter, CheckCounter callback function [Display Devices], CheckCounter, PFND3D10DDI_CHECKCOUNTER, PFND3D10DDI_CHECKCOUNTER, d3d10umddi/CheckCounter, UserModeDisplayDriverDx10_Functions_450a0976-fc56-4a5a-8a01-9c9d1041b628.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	CheckCounter
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D10DDI_CHECKCOUNTER callback function
The <b>CheckCounter</b> function retrieves information that describes a counter.

## Syntax

```
PFND3D10DDI_CHECKCOUNTER Pfnd3d10ddiCheckcounter;

void Pfnd3d10ddiCheckcounter(
   D3D10DDI_HDEVICE,
   D3D10DDI_QUERY,
  D3D10DDI_COUNTER_TYPE *,
  UINT *,
   LPSTR,
  UINT *pNameLength,
   LPSTR,
  UINT *pUnitsLength,
   LPSTR,
  UINT *pDescriptionLength
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_QUERY`



`*`



`*`



`LPSTR`



`*pNameLength`

A pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the <i>pName</i> parameter specifies.

`LPSTR`



`*pUnitsLength`

A pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the <i>pUnits</i> parameter specifies.

`LPSTR`



`*pDescriptionLength`

A pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the <i>pDescription</i> parameter specifies.


## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

The driver's <b>CheckCounter</b> function can call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set the ERR_UNSUPPORTED error code if the <i>Query</i> parameter of <b>CheckCounter</b>specifies a well-known counter that the device does not support.

The driver must validate a device-dependent counter identifier to ensure the identifier is within range. The driver must also ensure that enough space exists to copy each counter string into each buffer that the Microsoft Direct3D runtime provides. The driver can call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set the E_INVALIDARG error code if there is not enough space for any of the provided buffers.

The driver's <b>CheckCounter</b> function cannot call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set the D3DDDIERR_DEVICEREMOVED error code because <b>CheckCounter</b> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <b>CheckCounter</b>, even in the presence of D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CHECKCOUNTER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>