---
UID: NE:rilapitypes.RILUICCFILELOCKSTATUSACCESSCONDITION
title: RILUICCFILELOCKSTATUSACCESSCONDITION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfilelockstatusaccesscondition_2.htm
old-project: netvista
ms.assetid: f8bc0e66-1868-4e96-80d4-e541f6959eac
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILUICCFILELOCKSTATUSACCESSCONDITION, RILUICCFILELOCKSTATUSACCESSCONDITION enumeration [Network Drivers Starting with Windows Vista], RIL_UICCFILEACCESSCONDITION_ADM5, RIL_UICCFILEACCESSCONDITION_ADM6, RIL_UICCFILEACCESSCONDITION_MAX, RIL_UICCFILEACCESSCONDITION_NEV, RIL_UICCFILEACCESSCONDITION_PIN1, RIL_UICCFILEACCESSCONDITION_PIN2, RIL_UICCFILEACCESSCONDITION_RFU3, RIL_UICCFILEACCESSCONDITION_RFU4, netvista.riluiccfilelockstatusaccesscondition_2, rilapitypes/RILUICCFILELOCKSTATUSACCESSCONDITION, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM5, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM6, rilapitypes/RIL_UICCFILEACCESSCONDITION_MAX, rilapitypes/RIL_UICCFILEACCESSCONDITION_NEV, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN1, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN2, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU3, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU4
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILUICCFILELOCKSTATUSACCESSCONDITION
product: Windows
targetos: Windows
req.typenames: RILUICCFILELOCKSTATUSACCESSCONDITION
req.product: Windows 10 or later.
---

# RILUICCFILELOCKSTATUSACCESSCONDITION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCFILELOCKSTATUSACCESSCONDITION { 
  RIL_UICCFILEACCESSCONDITION_PIN1,
  RIL_UICCFILEACCESSCONDITION_PIN2,
  RIL_UICCFILEACCESSCONDITION_RFU3,
  RIL_UICCFILEACCESSCONDITION_RFU4,
  RIL_UICCFILEACCESSCONDITION_ADM5,
  RIL_UICCFILEACCESSCONDITION_ADM6,
  RIL_UICCFILEACCESSCONDITION_NEV,
  RIL_UICCFILEACCESSCONDITION_MAX
} RILUICCFILELOCKSTATUSACCESSCONDITION;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_ALW</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_PIN1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_PIN2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_RFU3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_RFU4</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_ADM5</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_ADM6</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_NEV</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCFILEACCESSCONDITION_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |