---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKCOUNTERINFO
title: PFND3D10DDI_CHECKCOUNTERINFO
author: windows-driver-content
description: The CheckCounterInfo function determines global information that is related to manipulating counters.
old-location: display\checkcounterinfo.htm
old-project: display
ms.assetid: 5dcea47c-aac7-46e5-afd5-c3390c3c5286
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.checkcounterinfo, CheckCounterInfo callback function [Display Devices], CheckCounterInfo, PFND3D10DDI_CHECKCOUNTERINFO, PFND3D10DDI_CHECKCOUNTERINFO, d3d10umddi/CheckCounterInfo, UserModeDisplayDriverDx10_Functions_7057ce5a-5677-4174-9bee-81c8ab5b18f7.xml
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
-	CheckCounterInfo
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D10DDI_CHECKCOUNTERINFO callback function
The <b>CheckCounterInfo</b> function determines global information that is related to manipulating counters.

## Syntax

```
PFND3D10DDI_CHECKCOUNTERINFO Pfnd3d10ddiCheckcounterinfo;

void Pfnd3d10ddiCheckcounterinfo(
   D3D10DDI_HDEVICE,
  D3D10DDI_COUNTER_INFO *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

If the user-mode display driver does not support any of the concepts that are represented in the members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_counter_info.md">D3D10DDI_COUNTER_INFO</a> structure, it can populate the members of D3D10DDI_COUNTER_INFO with zeros. 

The driver's <b>CheckCounterInfo</b> function cannot call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set the D3DDDIERR_DEVICEREMOVED error code because <b>CheckCounterInfo</b> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <b>CheckCounterInfo</b>, even in the presence of D3DDDIERR_DEVICEREMOVED. <b>CheckCounterInfo</b> should not encounter any errors. However, <b>CheckCounterInfo</b> might call <b>pfnSetErrorCb</b> for critical errors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_counter_info.md">D3D10DDI_COUNTER_INFO</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CHECKCOUNTERINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>