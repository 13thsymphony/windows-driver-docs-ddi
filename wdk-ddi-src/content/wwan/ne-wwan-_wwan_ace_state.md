---
UID: NE:wwan._WWAN_ACE_STATE
title: "_WWAN_ACE_STATE"
author: windows-driver-content
description: The WWAN_ACE_STATE enumeration lists the different kinds of auto-connect states.
old-location: netvista\wwan_ace_state.htm
old-project: netvista
ms.assetid: 6BF63894-58D6-4C7C-B3D9-D4D9D19A686B
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WwanManualOn, netvista.wwan_ace_state, wwan/WwanManualOff, wwan/WWAN_ACE_STATE, wwan/WwanAutoOn, wwan/WwanManualOn, WWAN_ACE_STATE, *PWWAN_ACE_STATE, WwanAutoOn, _WWAN_ACE_STATE, WwanAutoOff, wwan/WwanAutoOff, WwanManualOff, WWAN_ACE_STATE enumeration [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
-	wwan.h
apiname:
-	WWAN_ACE_STATE
product: Windows
targetos: Windows
req.typenames: "*PWWAN_ACE_STATE, WWAN_ACE_STATE"
req.product: Windows 10 or later.
---

# _WWAN_ACE_STATE Enumeration
The WWAN_ACE_STATE enumeration lists the different kinds of auto-connect states.

## Syntax
````
typedef enum _WWAN_ACE_STATE { 
  WwanAutoOff    = 0,
  WwanAutoOn     = ,
  WwanManualOff  = ,
  WwanManualOn   = 
} WWAN_ACE_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanAutoOff</td>
                    <td>Auto-connect off.</td>
                </tr>
            
                <tr>
                    <td>WwanAutoOn</td>
                    <td>Auto-connect on.</td>
                </tr>
            
                <tr>
                    <td>WwanManualOff</td>
                    <td>Manual connect off.</td>
                </tr>
            
                <tr>
                    <td>WwanManualOn</td>
                    <td>Manual connect on.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows 8 and later versions of Windows. Versions:\_Supported in Windows 8 and later versions of Windows. |
| **Header** | wwan.h |