---
UID: NE:61883.CMP_PLUG_LOCATION
title: CMP_PLUG_LOCATION
author: windows-driver-content
description: This enumeration specifies the location of a plug.
old-location: ieee\cmp_plug_location.htm
old-project: IEEE
ms.assetid: C46822B9-2263-4424-853B-32C726D83950
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 61883/CMP_PLUG_LOCATION, 61883/CMP_PlugLocal, 61883/CMP_PlugRemote, CMP_PLUG_LOCATION, CMP_PLUG_LOCATION enumeration [Buses], CMP_PlugLocal, CMP_PlugRemote, IEEE.cmp_plug_location
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: 61883.h
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
-	61883.h
api_name:
-	CMP_PLUG_LOCATION
product:
- Windows
targetos: Windows
req.typenames: CMP_PLUG_LOCATION
---

# CMP_PLUG_LOCATION Enumeration
This enumeration specifies the location of a plug.

## Syntax
```
typedef enum CMP_PLUG_LOCATION {
  CMP_PlugLocal   ,
  CMP_PlugRemote
} ;
```

## Constants

<table>
            
                <tr>
                    <td>CMP_PlugLocal</td>
                    <td>A local plug.</td>
                </tr>
            
                <tr>
                    <td>CMP_PlugRemote</td>
                    <td>A remote plug.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>