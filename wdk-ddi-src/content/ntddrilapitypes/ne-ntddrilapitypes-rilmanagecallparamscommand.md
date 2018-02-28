---
UID: NE:ntddrilapitypes.RILMANAGECALLPARAMSCOMMAND
title: RILMANAGECALLPARAMSCOMMAND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallparamscommand.htm
old-project: netvista
ms.assetid: d0344812-811e-47f6-a03b-bb753cce912a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMANAGECALLPARAMSCOMMAND, RILMANAGECALLPARAMSCOMMAND enumeration [Network Drivers Starting with Windows Vista], RIL_CALLCMD_ACCEPTINCOMINGCALL, RIL_CALLCMD_ADDHELDTOCONF, RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT, RIL_CALLCMD_ANSWERMEDIAOFFER, RIL_CALLCMD_ASSUREDCALLTRANSFER, RIL_CALLCMD_BLINDCALLTRANSFER, RIL_CALLCMD_CONSULTATIVECALLTRANSFER, RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD, RIL_CALLCMD_HOLDALLBUTONE, RIL_CALLCMD_MAX, RIL_CALLCMD_OFFERMEDIA, RIL_CALLCMD_RELEASEALLCALLS, RIL_CALLCMD_RELEASECALL, RIL_CALLCMD_RELEASEHELDCONFCALL, RIL_CALLCMD_RELEASEPROCEEDING, RIL_CALLCMD_RTT, netvista.rilmanagecallparamscommand, ntddrilapitypes/RILMANAGECALLPARAMSCOMMAND, ntddrilapitypes/RIL_CALLCMD_ACCEPTINCOMINGCALL, ntddrilapitypes/RIL_CALLCMD_ADDHELDTOCONF, ntddrilapitypes/RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT, ntddrilapitypes/RIL_CALLCMD_ANSWERMEDIAOFFER, ntddrilapitypes/RIL_CALLCMD_ASSUREDCALLTRANSFER, ntddrilapitypes/RIL_CALLCMD_BLINDCALLTRANSFER, ntddrilapitypes/RIL_CALLCMD_CONSULTATIVECALLTRANSFER, ntddrilapitypes/RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD, ntddrilapitypes/RIL_CALLCMD_HOLDALLBUTONE, ntddrilapitypes/RIL_CALLCMD_MAX, ntddrilapitypes/RIL_CALLCMD_OFFERMEDIA, ntddrilapitypes/RIL_CALLCMD_RELEASEALLCALLS, ntddrilapitypes/RIL_CALLCMD_RELEASECALL, ntddrilapitypes/RIL_CALLCMD_RELEASEHELDCONFCALL, ntddrilapitypes/RIL_CALLCMD_RELEASEPROCEEDING, ntddrilapitypes/RIL_CALLCMD_RTT
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
-	RILMANAGECALLPARAMSCOMMAND
product: Windows
targetos: Windows
req.typenames: RILMANAGECALLPARAMSCOMMAND
---

# RILMANAGECALLPARAMSCOMMAND Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMANAGECALLPARAMSCOMMAND { 
  RIL_CALLCMD_RELEASECALL,
  RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD,
  RIL_CALLCMD_HOLDALLBUTONE,
  RIL_CALLCMD_ADDHELDTOCONF,
  RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT,
  RIL_CALLCMD_RELEASEPROCEEDING,
  RIL_CALLCMD_RELEASEALLCALLS,
  RIL_CALLCMD_RELEASEHELDCONFCALL,
  RIL_CALLCMD_ACCEPTINCOMINGCALL,
  RIL_CALLCMD_OFFERMEDIA,
  RIL_CALLCMD_ANSWERMEDIAOFFER,
  RIL_CALLCMD_BLINDCALLTRANSFER,
  RIL_CALLCMD_ASSUREDCALLTRANSFER,
  RIL_CALLCMD_CONSULTATIVECALLTRANSFER,
  RIL_CALLCMD_RTT,
  RIL_CALLCMD_MAX
} RILMANAGECALLPARAMSCOMMAND;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CALLCMD_ACCEPTINCOMINGCALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_ADDHELDTOCONF</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_ADDHELDTOCONF_DISCONNECT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_ANSWERMEDIAOFFER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_ASSUREDCALLTRANSFER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_BLINDCALLTRANSFER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_CONSULTATIVECALLTRANSFER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_HOLDACTIVE_ACCEPTHELD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_HOLDALLBUTONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_OFFERMEDIA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_RELEASEACTIVE_ACCEPTHELD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_RELEASEALLCALLS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_RELEASECALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_RELEASEHELDCONFCALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_RELEASEPROCEEDING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLCMD_RTT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |