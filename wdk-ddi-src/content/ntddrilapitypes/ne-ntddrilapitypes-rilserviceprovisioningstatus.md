---
UID: NE:ntddrilapitypes.RILSERVICEPROVISIONINGSTATUS
title: RILSERVICEPROVISIONINGSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilserviceprovisioningstatus.htm
old-project: netvista
ms.assetid: 2f611dff-56b5-406f-8f67-cd3744caa1b5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSERVICEPROVISIONINGSTATUS, RILSERVICEPROVISIONINGSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_SVCPROV_MAX, RIL_SVCPROV_NOTPROVISIONED, RIL_SVCPROV_PROVISIONED, RIL_SVCPROV_TEMPMODEALLOWED, RIL_SVCPROV_TEMPMODERESTRICTED, netvista.rilserviceprovisioningstatus, ntddrilapitypes/RILSERVICEPROVISIONINGSTATUS, ntddrilapitypes/RIL_SVCPROV_MAX, ntddrilapitypes/RIL_SVCPROV_NOTPROVISIONED, ntddrilapitypes/RIL_SVCPROV_PROVISIONED, ntddrilapitypes/RIL_SVCPROV_TEMPMODEALLOWED, ntddrilapitypes/RIL_SVCPROV_TEMPMODERESTRICTED
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILSERVICEPROVISIONINGSTATUS
product: Windows
targetos: Windows
req.typenames: RILSERVICEPROVISIONINGSTATUS
---

# RILSERVICEPROVISIONINGSTATUS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSERVICEPROVISIONINGSTATUS { 
  RIL_SVCPROV_NOTPROVISIONED,
  RIL_SVCPROV_PROVISIONED,
  RIL_SVCPROV_TEMPMODERESTRICTED,
  RIL_SVCPROV_TEMPMODEALLOWED,
  RIL_SVCPROV_MAX
} RILSERVICEPROVISIONINGSTATUS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SVCPROV_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCPROV_NOTPROVISIONED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCPROV_PROVISIONED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCPROV_TEMPMODEALLOWED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCPROV_TEMPMODERESTRICTED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SVCPROV_UNKNOWN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |