---
UID: NS.RILAPITYPES.RILMSGINSTATUS~R1
title: RILMSGINSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsginstatus_2.htm
old-project: netvista
ms.assetid: 4dcc198f-5e42-4c60-bfec-19702c9ab674
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILMSGINSTATUS, RILMSGINSTATUS, *LPRILMSGINSTATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMSGINSTATUS
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
---

# RILMSGINSTATUS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef struct _RILMSGINSTATUS {
  DWORD                       dwMsgID;
  RILADDRESS                  raTgtRecipAddress;
  RILSYSTEMTIME               stTgtSCReceiveTime;
  RILSYSTEMTIME               stTgtDischargeTime;
  DWORD                       dwReserved;
  RILMSGINSTATUSTGTDLVSTATUS  dwTgtDlvStatus;
  RILMSGPROTOCOLID            dwProtocolID;
  RILMSGDCS                   rmdDataCoding;
  DWORD                       cbHdrLength;
  DWORD                       cchMsgLength;
  BYTE [MAXLENGTH_HDR]        rgbHdr;
  BYTE [MAXLENGTH_MSG]        rgbMsg;
} RILMSGINSTATUS, RILMSGINSTATUS;
````


## -struct-fields

### -field dwMsgID


### -field raTgtRecipAddress


### -field stTgtSCReceiveTime


### -field stTgtDischargeTime


### -field dwReserved


### -field dwTgtDlvStatus


### -field dwProtocolID


### -field rmdDataCoding


### -field cbHdrLength


### -field cchMsgLength


### -field rgbHdr


### -field rgbMsg


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>