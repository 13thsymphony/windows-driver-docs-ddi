---
UID: NE:ntddrilapitypes.RILMSGBCGENERALWARNINGTYPE
title: RILMSGBCGENERALWARNINGTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgbcgeneralwarningtype.htm
old-project: netvista
ms.assetid: c9d1a52e-e133-4fb5-a7a1-75699fe35cac
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_WARNINGTYPE_TSUNAMI, RILMSGBCGENERALWARNINGTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_WARNINGTYPE_OTHER, ntddrilapitypes/RIL_WARNINGTYPE_RESERVED, ntddrilapitypes/RILMSGBCGENERALWARNINGTYPE, RIL_WARNINGTYPE_EARTHQUAKETSUNAMI, RIL_WARNINGTYPE_MAX, RIL_WARNINGTYPE_TEST, ntddrilapitypes/RIL_WARNINGTYPE_TEST, ntddrilapitypes/RIL_WARNINGTYPE_OTHER, netvista.rilmsgbcgeneralwarningtype, ntddrilapitypes/RIL_WARNINGTYPE_TSUNAMI, ntddrilapitypes/RIL_WARNINGTYPE_EARTHQUAKETSUNAMI, RIL_WARNINGTYPE_RESERVED, ntddrilapitypes/RIL_WARNINGTYPE_MAX, RILMSGBCGENERALWARNINGTYPE
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
-	RILMSGBCGENERALWARNINGTYPE
product: Windows
targetos: Windows
req.typenames: RILMSGBCGENERALWARNINGTYPE
---

# RILMSGBCGENERALWARNINGTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGBCGENERALWARNINGTYPE { 
  RIL_WARNINGTYPE_TSUNAMI,
  RIL_WARNINGTYPE_EARTHQUAKETSUNAMI,
  RIL_WARNINGTYPE_TEST,
  RIL_WARNINGTYPE_OTHER,
  RIL_WARNINGTYPE_RESERVED,
  RIL_WARNINGTYPE_MAX
} RILMSGBCGENERALWARNINGTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_WARNINGTYPE_EARTHQUAKE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_WARNINGTYPE_EARTHQUAKETSUNAMI</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_WARNINGTYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_WARNINGTYPE_OTHER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_WARNINGTYPE_RESERVED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_WARNINGTYPE_TEST</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_WARNINGTYPE_TSUNAMI</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |