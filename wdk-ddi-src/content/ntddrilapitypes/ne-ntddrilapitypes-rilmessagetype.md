---
UID: NE:ntddrilapitypes.RILMESSAGETYPE
title: RILMESSAGETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagetype.htm
old-project: netvista
ms.assetid: 02960e7c-f1b2-4c28-9f9b-f180df3d9563
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILMESSAGETYPE, RILMESSAGETYPE enumeration [Network Drivers Starting with Windows Vista], RIL_MSGTYPE_BC_GENERAL, RIL_MSGTYPE_IN_CDMADELIVER, RIL_MSGTYPE_IN_IS637STATUS, RIL_MSGTYPE_IN_STATUS, RIL_MSGTYPE_OUT_CDMASUBMIT, RIL_MSGTYPE_OUT_SUBMIT, netvista.rilmessagetype, ntddrilapitypes/RILMESSAGETYPE, ntddrilapitypes/RIL_MSGTYPE_BC_GENERAL, ntddrilapitypes/RIL_MSGTYPE_IN_CDMADELIVER, ntddrilapitypes/RIL_MSGTYPE_IN_IS637STATUS, ntddrilapitypes/RIL_MSGTYPE_IN_STATUS, ntddrilapitypes/RIL_MSGTYPE_OUT_CDMASUBMIT, ntddrilapitypes/RIL_MSGTYPE_OUT_SUBMIT
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
-	RILMESSAGETYPE
product: Windows
targetos: Windows
req.typenames: RILMESSAGETYPE
---

# RILMESSAGETYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMESSAGETYPE { 
  RIL_MSGTYPE_IN_STATUS,
  RIL_MSGTYPE_IN_IS637STATUS,
  RIL_MSGTYPE_IN_CDMADELIVER,
  RIL_MSGTYPE_OUT_SUBMIT,
  RIL_MSGTYPE_OUT_CDMASUBMIT,
  RIL_MSGTYPE_BC_GENERAL
} RILMESSAGETYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGTYPE_BC_GENERAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGTYPE_IN_CDMADELIVER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGTYPE_IN_DELIVER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGTYPE_IN_IS637STATUS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGTYPE_IN_STATUS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGTYPE_OUT_CDMASUBMIT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGTYPE_OUT_SUBMIT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |