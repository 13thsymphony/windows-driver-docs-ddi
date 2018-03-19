---
UID: NE:iddcx.IDDCX_MONITOR_DESCRIPTION_TYPE
title: IDDCX_MONITOR_DESCRIPTION_TYPE
author: windows-driver-content
description: Used to describe the monitor description.
old-location: display\iddcx_monitor_description_type.htm
old-project: display
ms.assetid: ca50256b-2b37-4d39-ad4c-e2eaaa0adbb1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDDCX_MONITOR_DESCRIPTION_TYPE, IDDCX_MONITOR_DESCRIPTION_TYPE enumeration [Display Devices], IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID, IDDCX_MONITOR_DESCRIPTION_TYPE_EDID, IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED, display.iddcx_monitor_description_type, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_EDID, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iddcx.h
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
req.irql: "_requires_same_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_MONITOR_DESCRIPTION_TYPE
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_MONITOR_DESCRIPTION_TYPE Enumeration
Used to describe the monitor description.

## Syntax
````
typedef enum _IDDCX_MONITOR_DESCRIPTION_TYPE { 
  IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED  = 0,
  IDDCX_MONITOR_DESCRIPTION_TYPE_EDID           = 1,
  IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID      = 2
} IDDCX_MONITOR_DESCRIPTION_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED</td>
                    <td>Indicates that an <b>IDDCX_MONITOR_DESCRIPTION_TYPE</b> variable has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>IDDCX_MONITOR_DESCRIPTION_TYPE_EDID</td>
                    <td>The monitor description is EdId</td>
                </tr>
            
                <tr>
                    <td>IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID_AND_EDID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>UINT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |