---
UID: NE:ntddrilapitypes.RILMSGSERVICEINFOMSGSUPPORT
title: RILMSGSERVICEINFOMSGSUPPORT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgserviceinfomsgsupport.htm
old-project: netvista
ms.assetid: b09a5b1d-b8da-4a75-b2d5-ee07072d45aa
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSI_SMS_OUTGOING, ntddrilapitypes/RILMSGSERVICEINFOMSGSUPPORT, RILMSGSERVICEINFOMSGSUPPORT enumeration [Network Drivers Starting with Windows Vista], RIL_MSI_SMS_BROADCAST, ntddrilapitypes/RIL_MSI_SMS_OUTGOING, ntddrilapitypes/RIL_MSI_SMS_BROADCAST, netvista.rilmsgserviceinfomsgsupport, RILMSGSERVICEINFOMSGSUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILMSGSERVICEINFOMSGSUPPORT
product: Windows
targetos: Windows
req.typenames: RILMSGSERVICEINFOMSGSUPPORT
---

# RILMSGSERVICEINFOMSGSUPPORT Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGSERVICEINFOMSGSUPPORT { 
  RIL_MSI_SMS_OUTGOING,
  RIL_MSI_SMS_BROADCAST
} RILMSGSERVICEINFOMSGSUPPORT;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSI_SMS_BROADCAST</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSI_SMS_INCOMING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSI_SMS_OUTGOING</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |