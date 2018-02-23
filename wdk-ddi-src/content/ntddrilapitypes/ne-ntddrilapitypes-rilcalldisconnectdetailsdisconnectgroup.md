---
UID: NE:ntddrilapitypes.RILCALLDISCONNECTDETAILSDISCONNECTGROUP
title: RILCALLDISCONNECTDETAILSDISCONNECTGROUP
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetailsdisconnectgroup.htm
old-project: netvista
ms.assetid: d546e936-f8c6-45ad-8027-a8495b4633dc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RIL_CD_3GPP_NETWORK_CAUSE, ntddrilapitypes/RILCALLDISCONNECTDETAILSDISCONNECTGROUP, RIL_CD_3GPP_NETWORK_CAUSE, RILCALLDISCONNECTDETAILSDISCONNECTGROUP, RIL_CD_CAUSE_MAX, ntddrilapitypes/RIL_CD_3GPP2_VENDOR_CAUSE, RILCALLDISCONNECTDETAILSDISCONNECTGROUP enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CD_IMS_SIP_CAUSE, ntddrilapitypes/RIL_CD_AS_CAUSE, RIL_CD_3GPP2_VENDOR_CAUSE, ntddrilapitypes/RIL_CD_OTHER_CAUSE, netvista.rilcalldisconnectdetailsdisconnectgroup, ntddrilapitypes/RIL_CD_CAUSE_MAX, RIL_CD_AS_CAUSE, ntddrilapitypes/RIL_CD_3GPP_REJECT_CAUSE, RIL_CD_3GPP_REJECT_CAUSE, RIL_CD_IMS_SIP_CAUSE, RIL_CD_OTHER_CAUSE
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
-	RILCALLDISCONNECTDETAILSDISCONNECTGROUP
product: Windows
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILSDISCONNECTGROUP
---

# RILCALLDISCONNECTDETAILSDISCONNECTGROUP Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLDISCONNECTDETAILSDISCONNECTGROUP { 
  RIL_CD_AS_CAUSE,
  RIL_CD_3GPP_NETWORK_CAUSE,
  RIL_CD_3GPP2_VENDOR_CAUSE,
  RIL_CD_OTHER_CAUSE,
  RIL_CD_3GPP_REJECT_CAUSE,
  RIL_CD_IMS_SIP_CAUSE,
  RIL_CD_CAUSE_MAX
} RILCALLDISCONNECTDETAILSDISCONNECTGROUP;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CD_3GPP_NETWORK_CAUSE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_3GPP_REJECT_CAUSE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_3GPP2_VENDOR_CAUSE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_AS_CAUSE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_CAUSE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_IMS_SIP_CAUSE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_OTHER_CAUSE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_UNKNOWN_CAUSE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |