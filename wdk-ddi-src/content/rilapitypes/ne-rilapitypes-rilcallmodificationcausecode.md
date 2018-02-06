---
UID: NE:rilapitypes.RILCALLMODIFICATIONCAUSECODE
title: RILCALLMODIFICATIONCAUSECODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationcausecode_2.htm
old-project: netvista
ms.assetid: 44309e4e-a0a0-4aed-b942-2d15b8ab07dc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMODIFICATIONCAUSECODE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_CALL_MODIFIED_CAUSE_MAX, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, RIL_CALL_MODIFIED_CAUSE_MAX, RILCALLMODIFICATIONCAUSECODE, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, netvista.rilcallmodificationcausecode_2, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, rilapitypes/RILCALLMODIFICATIONCAUSECODE, *LPRILCALLMODIFICATIONCAUSECODE, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR
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
-	RILCALLMODIFICATIONCAUSECODE
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE"
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
| **Header** | rilapitypes.h |