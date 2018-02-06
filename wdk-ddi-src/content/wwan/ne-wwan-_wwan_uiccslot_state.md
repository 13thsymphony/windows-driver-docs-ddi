---
UID: NE:wwan._WWAN_UICCSLOT_STATE
title: "_WWAN_UICCSLOT_STATE"
author: windows-driver-content
description: The WWAN_UICCSLOT_STATE enumeration lists the different states of a UICC (SIM) card slot on a modem. The slot state represents a summary of both the slot state and the card state.
old-location: netvista\wwan_uiccslot_state.htm
old-project: netvista
ms.assetid: 63A3C2AA-6EBF-469D-933A-C51F5EC31C47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/UICCSlotStateEmpty, wwan/WWAN_UICCSLOT_STATE, WWAN_UICCSLOT_STATE enumeration [Network Drivers Starting with Windows Vista], wwan/UICCSlotStateUnknown, wwan/UICCSlotStateActive, wwan/UICCSlotStateOffEmpty, UICCSlotStateError, *PWWAN_UICCSLOT_STATE, UICCSlotStateOff, UICCSlotStateNotReady, netvista.wwan_uiccslot_state, _WWAN_UICCSLOT_STATE, wwan/UICCSlotStateNotReady, WWAN_UICCSLOT_STATE, wwan/UICCSlotStateOff, UICCSlotStateUnknown, UICCSlotStateEmpty, wwan/UICCSlotStateError, UICCSlotStateActive, UICCSlotStateOffEmpty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
-	WWAN_UICCSLOT_STATE
product: Windows
targetos: Windows
req.typenames: "*PWWAN_UICCSLOT_STATE, WWAN_UICCSLOT_STATE"
req.product: Windows 10 or later.
---

# _WWAN_UICCSLOT_STATE Enumeration
The <b>WWAN_UICCSLOT_STATE</b> enumeration lists the different states of a UICC (SIM) card slot on a modem. The slot state represents a summary of both the slot state and the card state.

## Syntax
````
typedef enum _WWAN_UICCSLOT_STATE { 
  UICCSlotStateUnknown,
  UICCSlotStateOffEmpty,
  UICCSlotStateOff,
  UICCSlotStateEmpty,
  UICCSlotStateNotReady,
  UICCSlotStateActive,
  UICCSlotStateError
} WWAN_UICCSLOT_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanUiccSlotStateActive</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateActiveEsim</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateActiveEsimNoProfile</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateEmpty</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateError</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateMax</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateNotReady</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateOff</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateOffEmpty</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanUiccSlotStateUnknown</td>
                    <td></td>
                </tr>
</table>

    ## Remarks

        The set of reported states is constrained by the capability of the slot hardware. In the most restrictive case, the slot hardware may only be able to determine that a card is present when it is powered on and active; in such a case the <b>OffEmpty</b> and <b>Off</b> states will not be reported.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1703 Windows 10, version 1703 |
| **Header** | wwan.h (include Wwan.h) |

    ## See Also

        <a href="..\wwan\ns-wwan-_wwan_slot_info.md">WWAN_SLOT_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_UICCSLOT_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>