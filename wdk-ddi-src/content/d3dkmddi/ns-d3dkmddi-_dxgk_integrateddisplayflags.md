---
UID: NS:d3dkmddi._DXGK_INTEGRATEDDISPLAYFLAGS
title: "_DXGK_INTEGRATEDDISPLAYFLAGS"
author: windows-driver-content
description: Flags which describe simple properties of an integrated display.
old-location: display\dxgk_integrateddisplayflags.htm
old-project: display
ms.assetid: 4671B6C1-358A-4CC2-A6FC-0FBA0F26DB07
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PDXGK_INTEGRATEDDISPLAYFLAGS, DXGK_INTEGRATEDDISPLAYFLAGS, DXGK_INTEGRATEDDISPLAYFLAGS union [Display Devices], _DXGK_INTEGRATEDDISPLAYFLAGS, d3dkmddi/DXGK_INTEGRATEDDISPLAYFLAGS, display.dxgk_integrateddisplayflags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_INTEGRATEDDISPLAYFLAGS
product:
- Windows
targetos: Windows
req.typenames: DXGK_INTEGRATEDDISPLAYFLAGS, *PDXGK_INTEGRATEDDISPLAYFLAGS
---

# _DXGK_INTEGRATEDDISPLAYFLAGS structure


## -description


Flags which describe simple properties of an integrated display.


## -struct-fields




### -field UndockedOrientation

Orientation of the integrated panel when the system is undocked.  
In most systems, the integrated panel is installed such that the native orientation of the panel matches the default orientation of the system so DXGK_DPO_0 (zero) would be used.  An example where this would be non-zero is if a natively portrait panel is used in a laptop device.



### -field DockedOrientation

Orientation of the integrated panel when the system is docked.  If the system does not support docking, this value will not be used.


In most systems, the integrated panel is installed such that the native orientation of the panel matches the default orientation of the system so DXGK_DPO_0 (zero) would be used.  An example where this would be non-zero is if a natively portrait panel is used in a small tablet and the dock holds the tablet in a landscape orientation.



### -field Reserved

This value is reserved for system use.


### -field Value

UINT used to operate on the combined bit-fields.

