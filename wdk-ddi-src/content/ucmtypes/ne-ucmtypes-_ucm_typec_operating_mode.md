---
UID: NE:ucmtypes._UCM_TYPEC_OPERATING_MODE
title: "_UCM_TYPEC_OPERATING_MODE"
author: windows-driver-content
description: Defines operating modes of a USB Type-C connector.
old-location: buses\ucm_type_c_operating_mode.htm
old-project: usbref
ms.assetid: B64849A6-DDB1-4BD1-B4B6-1E38DE9237E5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_TYPEC_OPERATING_MODE, UCM_TYPEC_OPERATING_MODE enumeration [Buses], UcmTypeCOperatingModeDfp, UcmTypeCOperatingModeDrp, UcmTypeCOperatingModeInvalid, UcmTypeCOperatingModeUfp, _UCM_TYPEC_OPERATING_MODE, buses.ucm_type_c_operating_mode, ucmtypes/UCM_TYPEC_OPERATING_MODE, ucmtypes/UcmTypeCOperatingModeDfp, ucmtypes/UcmTypeCOperatingModeDrp, ucmtypes/UcmTypeCOperatingModeInvalid, ucmtypes/UcmTypeCOperatingModeUfp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	Ucmtypes.h
api_name:
-	UCM_TYPEC_OPERATING_MODE
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_OPERATING_MODE
req.product: Windows 10 or later.
---

# _UCM_TYPEC_OPERATING_MODE Enumeration
Defines operating modes of a USB Type-C connector.

## Syntax
````
typedef enum _UCM_TYPEC_OPERATING_MODE { 
  UcmTypeCOperatingModeInvalid  = 0x0,
  UcmTypeCOperatingModeDfp      = 0x1,
  UcmTypeCOperatingModeUfp      = 0x2,
  UcmTypeCOperatingModeDrp      = 0x4
} UCM_TYPEC_OPERATING_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>UcmTypeCOperatingModeInvalid</td>
                    <td>Indicates the operating mode is invalid.</td>
                </tr>
            
                <tr>
                    <td>UcmTypeCOperatingModeDfp</td>
                    <td>Indicates the operating mode is set to downstream-facing port.</td>
                </tr>
            
                <tr>
                    <td>UcmTypeCOperatingModeUfp</td>
                    <td>Indicates the operating mode is set to upstream-facing port.</td>
                </tr>
            
                <tr>
                    <td>UcmTypeCOperatingModeDrp</td>
                    <td>Indicates the operating mode is set to dual-role port.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmtypes.h (include Ucmcx.h) |

## See Also

<a href="..\ucmmanager\nf-ucmmanager-ucm_connector_typec_config_init.md">UCM_CONNECTOR_TYPEC_CONFIG_INIT</a>