---
UID : NS:wwan._WWAN_SET_UICC_RESET
title : _WWAN_SET_UICC_RESET
author : windows-driver-content
description : The WWAN_SET_UICC_RESET structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC smart card.
old-location : netvista\wwan_set_uicc_reset.htm
old-project : netvista
ms.assetid : 33711459-70C8-43D2-974D-B90EC0DD8ED6
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WWAN_SET_UICC_RESET, *PWWAN_SET_UICC_RESET, WWAN_SET_UICC_RESET
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1709
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WWAN_SET_UICC_RESET
req.alt-loc : wwan.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PWWAN_SET_UICC_RESET, WWAN_SET_UICC_RESET"
req.product : Windows 10 or later.
---

# _WWAN_SET_UICC_RESET structure
The <b>WWAN_SET_UICC_RESET</b> structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a  UICC smart card.

## Syntax
````
typedef struct _WWAN_SET_UICC_RESET {
  WWAN_UICC_PASSTHROUGH_ACTION PassThroughAction;
} WWAN_SET_UICC_RESET, *PWWAN_SET_UICC_RESET;
````

## Members

        
            `PassThroughAction`

            The passthrough action specified by the host. For more info, see <a href="..\wwan\ne-wwan-_wwan_uicc_passthrough_action.md">WWAN_UICC_PASSTHROUGH_ACTION</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wwan.h (include Wwan.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_set_uicc_reset.md">NDIS_WWAN_SET_UICC_RESET</a>
</dt>
<dt>
<a href="..\wwan\ne-wwan-_wwan_uicc_passthrough_action.md">WWAN_UICC_PASSTHROUGH_ACTION</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SET_UICC_RESET structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>