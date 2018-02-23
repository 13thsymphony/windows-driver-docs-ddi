---
UID: NE:ntddrilapitypes.RILUICCAPPDATACHANGEENUM
title: RILUICCAPPDATACHANGEENUM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachangeenum.htm
old-project: netvista
ms.assetid: 6960080f-03dc-4c5f-8cd8-b96d030f2bd3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCAPPDATACHANGEENUM, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_MAX, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET, RIL_UICCAPP_DATACHANGE_MAX, ntddrilapitypes/RILUICCAPPDATACHANGEENUM, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_MBDN, RIL_UICCAPP_DATACHANGE_ESNME, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_ESNME, RIL_UICCAPP_DATACHANGE_MBDN, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET, RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET, RILUICCAPPDATACHANGEENUM enumeration [Network Drivers Starting with Windows Vista], RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET, netvista.riluiccappdatachangeenum
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
-	RILUICCAPPDATACHANGEENUM
product: Windows
targetos: Windows
req.typenames: RILUICCAPPDATACHANGEENUM
---

# RILUICCAPPDATACHANGEENUM Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCAPPDATACHANGEENUM { 
  RIL_UICCAPP_DATACHANGE_MBDN,
  RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET,
  RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET,
  RIL_UICCAPP_DATACHANGE_ESNME,
  RIL_UICCAPP_DATACHANGE_MAX
} RILUICCAPPDATACHANGEENUM;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCAPP_DATACHANGE_ESNME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCAPP_DATACHANGE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCAPP_DATACHANGE_MBDN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCAPP_DATACHANGE_MSISDN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |