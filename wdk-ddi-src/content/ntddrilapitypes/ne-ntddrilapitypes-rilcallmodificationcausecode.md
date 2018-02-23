---
UID: NE:ntddrilapitypes.RILCALLMODIFICATIONCAUSECODE
title: RILCALLMODIFICATIONCAUSECODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationcausecode.htm
old-project: netvista
ms.assetid: d2785ee2-6e5d-474e-9d0f-57da956b6ec7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLMODIFICATIONCAUSECODE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, *LPRILCALLMODIFICATIONCAUSECODE, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_MAX, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, netvista.rilcallmodificationcausecode, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, ntddrilapitypes/RILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, RIL_CALL_MODIFIED_CAUSE_MAX, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC
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
-	RILCALLMODIFICATIONCAUSECODE
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE"
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
| **Header** | ntddrilapitypes.h |