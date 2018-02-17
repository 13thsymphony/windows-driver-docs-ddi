---
UID: NE:ntddrilapitypes.RILSUPSVCINFOPARAMMASK
title: RILSUPSVCINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcinfoparammask.htm
old-project: netvista
ms.assetid: d3a4780f-6fd4-40d3-a629-5dad31720506
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARAM_SSI_CALL_FORWARDING_REASON, RIL_PARAM_SSI_CONNECTED_ID_SETTINGS, RIL_PARAM_SSI_SUPSERVICE_DATA, RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD, ntddrilapitypes/RIL_PARAM_SSI_CALLER_ID_SETTINGS, RILSUPSVCINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_SSI_SUPSERVICE_DATA, ntddrilapitypes/RIL_PARAM_SSI_FROM_NETWORK, ntddrilapitypes/RIL_PARAM_SSI_HIDE_ID_SETTINGS, RIL_PARAM_SSI_CALL_FORWARDING_REASON, RIL_PARAM_SSI_ALPHA_IDENTIFIER, ntddrilapitypes/RILSUPSVCINFOPARAMMASK, RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS, ntddrilapitypes/RIL_PARAM_SSI_DIALED_ID_SETTINGS, ntddrilapitypes/RIL_PARAM_SSI_ALL, RIL_PARAM_SSI_DIALED_ID_SETTINGS, netvista.rilsupsvcinfoparammask, ntddrilapitypes/RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD, ntddrilapitypes/RIL_PARAM_SSI_CALL_BARRING_TYPE, ntddrilapitypes/RIL_PARAM_SSI_INFOCLASSES, RIL_PARAM_SSI_SUPSVC_ACTION, ntddrilapitypes/RIL_PARAM_SSI_SUPSVC_ACTION, RIL_PARAM_SSI_ALL, RIL_PARAM_SSI_FROM_NETWORK, RIL_PARAM_SSI_SUPSVC_TYPE, ntddrilapitypes/RIL_PARAM_SSI_SUPSVC_TYPE, RIL_PARAM_SSI_FAILURE_REASON, RILSUPSVCINFOPARAMMASK, RIL_PARAM_SSI_INFOCLASSES, RIL_PARAM_SSI_CALL_BARRING_PASSWORD, ntddrilapitypes/RIL_PARAM_SSI_CALL_BARRING_PASSWORD, ntddrilapitypes/RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS, RIL_PARAM_SSI_CALLER_ID_SETTINGS, ntddrilapitypes/RIL_PARAM_SSI_ALPHA_IDENTIFIER, RIL_PARAM_SSI_HIDE_ID_SETTINGS, ntddrilapitypes/RIL_PARAM_SSI_CONNECTED_ID_SETTINGS, RIL_PARAM_SSI_CALL_BARRING_TYPE, ntddrilapitypes/RIL_PARAM_SSI_FAILURE_REASON
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
-	RILSUPSVCINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSUPSVCINFOPARAMMASK
---

# RILSUPSVCINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSUPSVCINFOPARAMMASK { 
  RIL_PARAM_SSI_FROM_NETWORK,
  RIL_PARAM_SSI_FAILURE_REASON,
  RIL_PARAM_SSI_SUPSVC_ACTION,
  RIL_PARAM_SSI_SUPSVC_TYPE,
  RIL_PARAM_SSI_CALL_FORWARDING_REASON,
  RIL_PARAM_SSI_CALL_BARRING_TYPE,
  RIL_PARAM_SSI_INFOCLASSES,
  RIL_PARAM_SSI_ALPHA_IDENTIFIER,
  RIL_PARAM_SSI_CALL_BARRING_PASSWORD,
  RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD,
  RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS,
  RIL_PARAM_SSI_CALLER_ID_SETTINGS,
  RIL_PARAM_SSI_DIALED_ID_SETTINGS,
  RIL_PARAM_SSI_HIDE_ID_SETTINGS,
  RIL_PARAM_SSI_CONNECTED_ID_SETTINGS,
  RIL_PARAM_SSI_SUPSERVICE_DATA,
  RIL_PARAM_SSI_ALL
} RILSUPSVCINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_SSI_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_ALPHA_IDENTIFIER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_CALL_BARRING_PASSWORD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_CALL_BARRING_TYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_CALL_FORWARDING_REASON</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_CALLER_ID_SETTINGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_CONNECTED_ID_SETTINGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_DIALED_ID_SETTINGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_FAILURE_REASON</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_FROM_NETWORK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_HIDE_ID_SETTINGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_INFOCLASSES</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_SUPSERVICE_DATA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_SUPSVC_ACTION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSI_SUPSVC_TYPE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |