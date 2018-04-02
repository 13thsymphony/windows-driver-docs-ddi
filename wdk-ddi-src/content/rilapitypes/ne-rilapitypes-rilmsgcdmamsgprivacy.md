---
UID: NE:rilapitypes.RILMSGCDMAMSGPRIVACY
title: RILMSGCDMAMSGPRIVACY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgprivacy.htm
old-project: netvista
ms.assetid: 491b985f-c228-4f4b-88c1-fd678266dd9d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILMSGCDMAMSGPRIVACY, RILMSGCDMAMSGPRIVACY enumeration [Network Drivers Starting with Windows Vista], RIL_MSGPRIVACYCLASS_CONFIDENTIAL, RIL_MSGPRIVACYCLASS_MAX, RIL_MSGPRIVACYCLASS_RESTRICTED, RIL_MSGPRIVACYCLASS_SECRET, netvista.rilmsgcdmamsgprivacy, ntddrilapitypes/RILMSGCDMAMSGPRIVACY, ntddrilapitypes/RIL_MSGPRIVACYCLASS_CONFIDENTIAL, ntddrilapitypes/RIL_MSGPRIVACYCLASS_MAX, ntddrilapitypes/RIL_MSGPRIVACYCLASS_RESTRICTED, ntddrilapitypes/RIL_MSGPRIVACYCLASS_SECRET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILMSGCDMAMSGPRIVACY
product: Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGPRIVACY
req.product: Windows 10 or later.
---

# RILMSGCDMAMSGPRIVACY Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILMSGCDMAMSGPRIVACY {
  RIL_MSGPRIVACYCLASS_NOTRESTRICTED  ,
  RIL_MSGPRIVACYCLASS_RESTRICTED     ,
  RIL_MSGPRIVACYCLASS_CONFIDENTIAL   ,
  RIL_MSGPRIVACYCLASS_SECRET         ,
  RIL_MSGPRIVACYCLASS_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGPRIVACYCLASS_NOTRESTRICTED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIVACYCLASS_RESTRICTED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIVACYCLASS_CONFIDENTIAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIVACYCLASS_SECRET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIVACYCLASS_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |