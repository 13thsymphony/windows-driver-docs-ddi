---
UID: NE:rilapitypes.RILUICCAPPDATACHANGEENUM
title: RILUICCAPPDATACHANGEENUM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachangeenum_2.htm
old-project: netvista
ms.assetid: 66d5596b-5f5b-46a6-9151-074c4713940f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCAPPDATACHANGEENUM, rilapitypes/RIL_UICCAPP_DATACHANGE_ESNME, RIL_UICCAPP_DATACHANGE_MAX, rilapitypes/RILUICCAPPDATACHANGEENUM, rilapitypes/RIL_UICCAPP_DATACHANGE_MBDN, RIL_UICCAPP_DATACHANGE_ESNME, RIL_UICCAPP_DATACHANGE_MBDN, netvista.riluiccappdatachangeenum_2, rilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET, RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET, rilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET, RILUICCAPPDATACHANGEENUM enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_UICCAPP_DATACHANGE_MAX, RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILUICCAPPDATACHANGEENUM
product: Windows
targetos: Windows
req.typenames: RILUICCAPPDATACHANGEENUM
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |