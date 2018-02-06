---
UID: NE:rilapitypes.RILMSGSERVICEINFOMSGSUPPORT
title: RILMSGSERVICEINFOMSGSUPPORT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgserviceinfomsgsupport_2.htm
old-project: netvista
ms.assetid: e9e1f353-4501-487d-ba2d-ee1572d93507
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSI_SMS_OUTGOING, RILMSGSERVICEINFOMSGSUPPORT, RIL_MSI_SMS_BROADCAST, rilapitypes/RIL_MSI_SMS_BROADCAST, netvista.rilmsgserviceinfomsgsupport_2, RILMSGSERVICEINFOMSGSUPPORT enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILMSGSERVICEINFOMSGSUPPORT, rilapitypes/RIL_MSI_SMS_OUTGOING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILMSGSERVICEINFOMSGSUPPORT
product: Windows
targetos: Windows
req.typenames: RILMSGSERVICEINFOMSGSUPPORT
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |