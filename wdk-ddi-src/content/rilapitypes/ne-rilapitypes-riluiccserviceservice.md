---
UID: NE:rilapitypes.RILUICCSERVICESERVICE
title: RILUICCSERVICESERVICE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccserviceservice_2.htm
old-project: netvista
ms.assetid: bc3df2dd-caa7-4614-a243-3df13e3c0e84
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_UICCOPERATION_SERVICE_ACL, RIL_UICCOPERATION_SERVICE_MAX, rilapitypes/RIL_UICCOPERATION_SERVICE_MAX, netvista.riluiccserviceservice_2, RILUICCSERVICESERVICE, rilapitypes/RIL_UICCOPERATION_SERVICE_ACL, RILUICCSERVICESERVICE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCOPERATION_SERVICE_BDN, rilapitypes/RILUICCSERVICESERVICE, rilapitypes/RIL_UICCOPERATION_SERVICE_BDN
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
-	RILUICCSERVICESERVICE
product: Windows
targetos: Windows
req.typenames: RILUICCSERVICESERVICE
req.product: Windows 10 or later.
---

# RILUICCSERVICESERVICE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCSERVICESERVICE { 
  RIL_UICCOPERATION_SERVICE_BDN,
  RIL_UICCOPERATION_SERVICE_ACL,
  RIL_UICCOPERATION_SERVICE_MAX
} RILUICCSERVICESERVICE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_UICCOPERATION_SERVICE_ACL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCOPERATION_SERVICE_BDN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCOPERATION_SERVICE_FDN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCOPERATION_SERVICE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |