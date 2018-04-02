---
UID: NC:d3dumddi.PFND3DDDI_CHECKCOUNTERINFO
title: PFND3DDDI_CHECKCOUNTERINFO
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to determine global information that's related to manipulating counters. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfncheckcounterinfo.htm
old-project: display
ms.assetid: 98B8EE79-18D2-4C57-964B-74DB550C1330
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_CHECKCOUNTERINFO, d3dumddi/pfnCheckCounterInfo, display.pfncheckcounterinfo, pfnCheckCounterInfo, pfnCheckCounterInfo callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
api_name:
-	pfnCheckCounterInfo
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CHECKCOUNTERINFO callback function
Called by the Microsoft Direct3D runtime to determine global information that's related to manipulating counters. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## Syntax

```
PFND3DDDI_CHECKCOUNTERINFO Pfnd3dddiCheckcounterinfo;

void Pfnd3dddiCheckcounterinfo(
  HANDLE hDevice,
  D3DDDIARG_COUNTER_INFO *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

This function should behave similarly to the <a href="https://msdn.microsoft.com/5dcea47c-aac7-46e5-afd5-c3390c3c5286">CheckCounterInfo</a> function that supports Microsoft Direct3D 10 and later.

If the user-mode display driver does not support any of the concepts that are represented in the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn449152">D3DDDIARG_COUNTER_INFO</a> structure, it can populate the members of <b>D3DDDIARG_COUNTER_INFO</b> with zeros.

The driver's <i>pfnCheckCounterInfo</i> function cannot call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set the <b>D3DDDIERR_DEVICEREMOVED</b> error code because <i>pfnCheckCounterInfo</i> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <i>pfnCheckCounterInfo</i>, even in the presence of <b>D3DDDIERR_DEVICEREMOVED</b>. <i>pfnCheckCounterInfo</i> should not encounter any errors. However, <i>pfnCheckCounterInfo</i> might call <b>pfnSetErrorCb</b> for critical errors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/5dcea47c-aac7-46e5-afd5-c3390c3c5286">CheckCounterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn449152">D3DDDIARG_COUNTER_INFO</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>