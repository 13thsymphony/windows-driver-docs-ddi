---
UID: NE:wwan._WWAN_ACTIVATION_STATE
title: "_WWAN_ACTIVATION_STATE"
author: windows-driver-content
description: The WWAN_ACTIVATION_STATE enumeration lists the different Packet Data Protocol (PDP) context activation states that are supported by the MB device.
old-location: netvista\wwan_activation_state.htm
old-project: netvista
ms.assetid: ca5caf9d-5c73-4516-bbc9-ee3ff9511e99
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_ACTIVATION_STATE, PWWAN_ACTIVATION_STATE, PWWAN_ACTIVATION_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_ACTIVATION_STATE, WWAN_ACTIVATION_STATE enumeration [Network Drivers Starting with Windows Vista], WwanActivationStateActivated, WwanActivationStateActivating, WwanActivationStateDeactivated, WwanActivationStateDeactivating, WwanActivationStateMax, WwanActivationStateUnknown, WwanRef_d1e0cf59-316c-45a2-8ae3-231c30cae091.xml, _WWAN_ACTIVATION_STATE, netvista.wwan_activation_state, wwan/PWWAN_ACTIVATION_STATE, wwan/WWAN_ACTIVATION_STATE, wwan/WwanActivationStateActivated, wwan/WwanActivationStateActivating, wwan/WwanActivationStateDeactivated, wwan/WwanActivationStateDeactivating, wwan/WwanActivationStateMax, wwan/WwanActivationStateUnknown"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
api_name:
-	WWAN_ACTIVATION_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_ACTIVATION_STATE, *PWWAN_ACTIVATION_STATE
req.product: Windows 10 or later.
---

# _WWAN_ACTIVATION_STATE Enumeration
The WWAN_ACTIVATION_STATE enumeration lists the different Packet Data Protocol (PDP) context
  activation states that are supported by the MB device.

## Syntax
````
typedef enum _WWAN_ACTIVATION_STATE { 
  WwanActivationStateUnknown       = 0,
  WwanActivationStateActivated,
  WwanActivationStateActivating,
  WwanActivationStateDeactivated,
  WwanActivationStateDeactivating,
  WwanActivationStateMax
} WWAN_ACTIVATION_STATE, *PWWAN_ACTIVATION_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanActivationStateUnknown</td>
                    <td>The activation state is unknown.</td>
                </tr>
            
                <tr>
                    <td>WwanActivationStateActivated</td>
                    <td>The packet context is activated.</td>
                </tr>
            
                <tr>
                    <td>WwanActivationStateActivating</td>
                    <td>The packet context is currently in the process of getting activated.</td>
                </tr>
            
                <tr>
                    <td>WwanActivationStateDeactivated</td>
                    <td>The packet context is not activated.</td>
                </tr>
            
                <tr>
                    <td>WwanActivationStateDeactivating</td>
                    <td>The packet context is currently in the process of getting deactivated.</td>
                </tr>
            
                <tr>
                    <td>WwanActivationStateMax</td>
                    <td>The total number of PDP activation states.</td>
                </tr>
</table>

## Remarks

Miniport drivers use the 
    <b>WwanActivationStateActivating</b> and 
    <b>WwanActivationStateDeactivating</b> transient states when responding to 
    <i>query</i> requests. Miniport driver should not return these states when processing 
    <i>set</i> requests. Miniport drivers must only send 
    <i>set</i> indications after they have successfully activated or deactivated a PDP context, and not
    immediately after receiving the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_set_context_state.md">WWAN_SET_CONTEXT_STATE</a>