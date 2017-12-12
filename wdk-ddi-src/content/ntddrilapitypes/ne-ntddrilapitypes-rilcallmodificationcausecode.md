---
UID: NE.ntddrilapitypes.RILCALLMODIFICATIONCAUSECODE
title: RILCALLMODIFICATIONCAUSECODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationcausecode.htm
old-project: netvista
ms.assetid: d2785ee2-6e5d-474e-9d0f-57da956b6ec7
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILCALLMODIFICATIONCAUSECODE, *LPRILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE
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
req.alt-api: RILCALLMODIFICATIONCAUSECODE
req.alt-loc: ntddrilapitypes.h
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
---

# RILCALLMODIFICATIONCAUSECODE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

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


## -enum-fields

### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT


### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS


### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS


### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT


### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION


### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC


### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR


### -field RIL_CALL_MODIFIED_CAUSE_MAX


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>