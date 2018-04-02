---
UID: NE:bthddi._SCO_LINK_TYPE
title: "_SCO_LINK_TYPE"
author: windows-driver-content
description: The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a ScoIndicationRemoteConnect indication event is processed.
old-location: bltooth\sco_link_type.htm
old-project: bltooth
ms.assetid: 6867a88d-6bce-46eb-894a-cc034a1c3ece
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSCO_LINK_TYPE, PSCO_LINK_TYPE, PSCO_LINK_TYPE enumeration pointer [Bluetooth Devices], SCO_LINK_TYPE, SCO_LINK_TYPE enumeration [Bluetooth Devices], ScoLinkType, _SCO_LINK_TYPE, bltooth.sco_link_type, bth_enums_c5b9357f-7046-4115-a8a7-add459e59f27.xml, bthddi/PSCO_LINK_TYPE, bthddi/SCO_LINK_TYPE, bthddi/ScoLinkType, bthddi/eScoLinkType, eScoLinkType"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	SCO_LINK_TYPE
product: Windows
targetos: Windows
req.typenames: SCO_LINK_TYPE, *PSCO_LINK_TYPE
---

# _SCO_LINK_TYPE Enumeration
The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a 
  <b>ScoIndicationRemoteConnect</b> indication event is processed.

## Syntax
```
typedef enum _SCO_LINK_TYPE {
  ScoLinkType   ,
  eScoLinkType
} SCO_LINK_TYPE, *PSCO_LINK_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>ScoLinkType</td>
                    <td>This value indicates that the link used by the connection is a SCO link.</td>
                </tr>
            
                <tr>
                    <td>eScoLinkType</td>
                    <td>This value indicates that the link used by the connection is an eSCO link.</td>
                </tr>
</table>

## Remarks

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536779">SCO_INDICATION_PARAMETERS</a> structure
    uses this enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536779">SCO_INDICATION_PARAMETERS</a>