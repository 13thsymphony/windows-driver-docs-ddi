---
UID: NE:rilapitypes.RILCALLMODIFICATIONCAUSECODE
title: RILCALLMODIFICATIONCAUSECODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationcausecode.htm
old-project: netvista
ms.assetid: d2785ee2-6e5d-474e-9d0f-57da956b6ec7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE enumeration [Network Drivers Starting with Windows Vista], RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, RIL_CALL_MODIFIED_CAUSE_MAX, netvista.rilcallmodificationcausecode, ntddrilapitypes/RILCALLMODIFICATIONCAUSECODE, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_MAX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILCALLMODIFICATIONCAUSECODE
product: Windows
targetos: Windows
req.typenames: RILCALLMODIFICATIONCAUSECODE, *LPRILCALLMODIFICATIONCAUSECODE
req.product: Windows 10 or later.
---

# RILCALLMODIFICATIONCAUSECODE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLMODIFICATIONCAUSECODE { 
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR,
  RIL_CALL_MODIFIED_CAUSE_MAX
} RILCALLMODIFICATIONCAUSECODE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MODIFIED_CAUSE_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |