---
UID: NE:ntddrilapitypes.RILIMSFAILUREMESSAGETYPE
title: RILIMSFAILUREMESSAGETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsfailuremessagetype.htm
old-project: netvista
ms.assetid: e40241e6-90ee-4bbb-8fde-f52ffd838c1f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILIMSFAILUREMESSAGETYPE, RILIMSFAILUREMESSAGETYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSFAILUREMESSAGETYPE_INCALL, RIL_IMSFAILUREMESSAGETYPE_MAX, RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE, netvista.rilimsfailuremessagetype, ntddrilapitypes/RILIMSFAILUREMESSAGETYPE, ntddrilapitypes/RIL_IMSFAILUREMESSAGETYPE_INCALL, ntddrilapitypes/RIL_IMSFAILUREMESSAGETYPE_MAX, ntddrilapitypes/RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE
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
-	RILIMSFAILUREMESSAGETYPE
product: Windows
targetos: Windows
req.typenames: RILIMSFAILUREMESSAGETYPE
---

# RILIMSFAILUREMESSAGETYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILIMSFAILUREMESSAGETYPE { 
  RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE,
  RIL_IMSFAILUREMESSAGETYPE_INCALL,
  RIL_IMSFAILUREMESSAGETYPE_MAX
} RILIMSFAILUREMESSAGETYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_IMSFAILUREMESSAGETYPE_INCALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSFAILUREMESSAGETYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSFAILUREMESSAGETYPE_REGISTER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |