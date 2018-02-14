---
UID: NE:iddcx.IDDCX_UPDATE_REASON
title: IDDCX_UPDATE_REASON
author: windows-driver-content
description: Describes why the driver is calling to update the mode list.
old-location: display\iddcx_update_reason.htm
old-project: display
ms.assetid: e451e4e3-0b8a-4a17-8e4e-2da99d336a39
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: iddcx/IDDCX_UPDATE_REASON, iddcx/IDDCX_UPDATE_REASON_OTHER, IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH, iddcx/IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS, IDDCX_UPDATE_REASON, IDDCX_UPDATE_REASON enumeration [Display Devices], IDDCX_UPDATE_REASON_OTHER, IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS, IDDCX_UPDATE_REASON_UNINITIALIZED, IDDCX_UPDATE_REASON_POWER_CONSTRAINTS, iddcx/IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH, IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH, display.iddcx_update_reason, iddcx/IDDCX_UPDATE_REASON_UNINITIALIZED, iddcx/IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH, iddcx/IDDCX_UPDATE_REASON_POWER_CONSTRAINTS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDDCX_UPDATE_REASON
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_UPDATE_REASON Enumeration
Describes why the driver is calling to update the mode list

## Syntax
````
typedef enum _IDDCX_UPDATE_REASON { 
  IDDCX_UPDATE_REASON_UNINITIALIZED              = 0,
  IDDCX_UPDATE_REASON_POWER_CONSTRAINTS          = 1,
  IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH        = 2,
  IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH     = 3,
  IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS  = 4,
  IDDCX_UPDATE_REASON_OTHER                      = 5
} IDDCX_UPDATE_REASON;
````

## Constants

<table>
            
                <tr>
                    <td>IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS</td>
                    <td>The mode list is changing due to constraints of the product when in a new configuration</td>
                </tr>
            
                <tr>
                    <td>IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH</td>
                    <td>The mode list is changing due to changes in bandwidth between the indirect display device and the monitor</td>
                </tr>
            
                <tr>
                    <td>IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH</td>
                    <td>The mode list is changing due to changes in bandwidth between the system and the indirect display device</td>
                </tr>
            
                <tr>
                    <td>IDDCX_UPDATE_REASON_OTHER</td>
                    <td>The mode list is changing due to another reason not listed above</td>
                </tr>
            
                <tr>
                    <td>IDDCX_UPDATE_REASON_POWER_CONSTRAINTS</td>
                    <td>The mode list is changing due to changed power constraints on the host system</td>
                </tr>
            
                <tr>
                    <td>IDDCX_UPDATE_REASON_UNINITIALIZED</td>
                    <td>Indicates that an <b>IDDCX_UPDATE_REASON</b> variable has not yet been assigned a meaningful value.</td>
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