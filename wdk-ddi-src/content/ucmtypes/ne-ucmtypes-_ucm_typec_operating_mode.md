---
UID: NE:ucmtypes._UCM_TYPEC_OPERATING_MODE
title: "_UCM_TYPEC_OPERATING_MODE"
author: windows-driver-content
description: Defines operating modes of a USB Type-C connector.
old-location: buses\ucm_type_c_operating_mode.htm
old-project: usbref
ms.assetid: B64849A6-DDB1-4BD1-B4B6-1E38DE9237E5
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UCM_TYPEC_OPERATING_MODE, buses.ucm_type_c_operating_mode, UCM_TYPEC_OPERATING_MODE enumeration [Buses], UcmTypeCOperatingModeUfp, UcmTypeCOperatingModeDrp, ucmtypes/UcmTypeCOperatingModeDrp, ucmtypes/UCM_TYPEC_OPERATING_MODE, UcmTypeCOperatingModeDfp, _UCM_TYPEC_OPERATING_MODE, ucmtypes/UcmTypeCOperatingModeInvalid, UcmTypeCOperatingModeInvalid, ucmtypes/UcmTypeCOperatingModeUfp, ucmtypes/UcmTypeCOperatingModeDfp
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucmtypes.h
apiname:
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
                    <td>UcmTypeCOperatingModeDfp</td>
                    <td>Indicates the operating mode is set to downstream-facing port.</td>
                </tr>
            
                <tr>
                    <td>UcmTypeCOperatingModeDrp</td>
                    <td>Indicates the operating mode is set to dual-role port.</td>
                </tr>
            
                <tr>
                    <td>UcmTypeCOperatingModeInvalid</td>
                    <td>Indicates the operating mode is invalid.</td>
                </tr>
            
                <tr>
                    <td>UcmTypeCOperatingModeUfp</td>
                    <td>Indicates the operating mode is set to upstream-facing port.</td>
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_TYPEC_OPERATING_MODE enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>