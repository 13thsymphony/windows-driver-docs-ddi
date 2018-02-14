---
UID: NE:wwan._WWAN_ACTIVATION_STATE
title: "_WWAN_ACTIVATION_STATE"
author: windows-driver-content
description: The WWAN_ACTIVATION_STATE enumeration lists the different Packet Data Protocol (PDP) context activation states that are supported by the MB device.
old-location: netvista\wwan_activation_state.htm
old-project: netvista
ms.assetid: ca5caf9d-5c73-4516-bbc9-ee3ff9511e99
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PWWAN_ACTIVATION_STATE enumeration pointer [Network Drivers Starting with Windows Vista], wwan/WwanActivationStateActivating, WwanActivationStateUnknown, _WWAN_ACTIVATION_STATE, wwan/WwanActivationStateUnknown, wwan/WwanActivationStateMax, wwan/WwanActivationStateDeactivating, WwanActivationStateActivating, wwan/WWAN_ACTIVATION_STATE, PWWAN_ACTIVATION_STATE, WwanActivationStateDeactivating, WwanActivationStateActivated, WWAN_ACTIVATION_STATE enumeration [Network Drivers Starting with Windows Vista], *PWWAN_ACTIVATION_STATE, WWAN_ACTIVATION_STATE, WwanActivationStateDeactivated, WwanActivationStateMax, netvista.wwan_activation_state, wwan/PWWAN_ACTIVATION_STATE, wwan/WwanActivationStateActivated, WwanRef_d1e0cf59-316c-45a2-8ae3-231c30cae091.xml, wwan/WwanActivationStateDeactivated
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_ACTIVATION_STATE
product: Windows
targetos: Windows
req.typenames: "*PWWAN_ACTIVATION_STATE, WWAN_ACTIVATION_STATE"
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
            
                <tr>
                    <td>WwanActivationStateUnknown</td>
                    <td>The activation state is unknown.</td>
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_ACTIVATION_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>