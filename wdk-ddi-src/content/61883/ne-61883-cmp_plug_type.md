---
UID: NE:61883.CMP_PLUG_TYPE
title: CMP_PLUG_TYPE
author: windows-driver-content
description: This enumeration specifies the type of a plug.
old-location: ieee\cmp_plug_type.htm
old-project: IEEE
ms.assetid: 97A19F3D-5669-4E4B-A377-7BE5A84DF63A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 61883/CMP_PLUG_TYPE, 61883/CMP_PlugIn, 61883/CMP_PlugOut, CMP_PLUG_TYPE, CMP_PLUG_TYPE enumeration [Buses], CMP_PlugIn, CMP_PlugOut, IEEE.cmp_plug_type
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
-	CMP_PLUG_TYPE
product:
- Windows
targetos: Windows
req.typenames: CMP_PLUG_TYPE
---

# CMP_PLUG_TYPE Enumeration
This enumeration specifies the type of a plug.

## Syntax
```
typedef enum CMP_PLUG_TYPE {
  CMP_PlugOut  ,
  CMP_PlugIn
} ;
```

## Constants

<table>
            
                <tr>
                    <td>CMP_PlugOut</td>
                    <td>An out plug.</td>
                </tr>
            
                <tr>
                    <td>CMP_PlugIn</td>
                    <td>An in plug.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>