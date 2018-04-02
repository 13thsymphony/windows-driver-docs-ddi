---
UID: NE:ntddrilapitypes.RILMSGCDMAMSGDISPLAYMODE
title: RILMSGCDMAMSGDISPLAYMODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgdisplaymode.htm
old-project: netvista
ms.assetid: ee75cf74-def7-4705-ae61-c2472bd4446e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILMSGCDMAMSGDISPLAYMODE, RILMSGCDMAMSGDISPLAYMODE enumeration [Network Drivers Starting with Windows Vista], RIL_MSGDISPLAYMODE_MAX, RIL_MSGDISPLAYMODE_MOBILEDEFAULT, RIL_MSGDISPLAYMODE_USERDEFAULT, netvista.rilmsgcdmamsgdisplaymode, ntddrilapitypes/RILMSGCDMAMSGDISPLAYMODE, ntddrilapitypes/RIL_MSGDISPLAYMODE_MAX, ntddrilapitypes/RIL_MSGDISPLAYMODE_MOBILEDEFAULT, ntddrilapitypes/RIL_MSGDISPLAYMODE_USERDEFAULT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	RILMSGCDMAMSGDISPLAYMODE
product:
- Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGDISPLAYMODE
---

# RILMSGCDMAMSGDISPLAYMODE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILMSGCDMAMSGDISPLAYMODE {
  RIL_MSGDISPLAYMODE_IMMEDIATE      ,
  RIL_MSGDISPLAYMODE_MOBILEDEFAULT  ,
  RIL_MSGDISPLAYMODE_USERDEFAULT    ,
  RIL_MSGDISPLAYMODE_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGDISPLAYMODE_IMMEDIATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGDISPLAYMODE_MOBILEDEFAULT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGDISPLAYMODE_USERDEFAULT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGDISPLAYMODE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |