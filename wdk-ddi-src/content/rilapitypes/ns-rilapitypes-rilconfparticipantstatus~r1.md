---
UID: NS.RILAPITYPES.RILCONFPARTICIPANTSTATUS~R1
title: RILCONFPARTICIPANTSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilconfparticipantstatus_2.htm
old-project: netvista
ms.assetid: 3beafad2-7157-434a-a073-2b47026c8fc5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILCONFPARTICIPANTSTATUS, *LPRILCONFPARTICIPANTSTATUS, RILCONFPARTICIPANTSTATUS
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
req.alt-api: RILCONFPARTICIPANTSTATUS
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

# RILCONFPARTICIPANTSTATUS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef struct _RILCONFPARTICIPANTSTATUS {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwExecutor;
  DWORD                    dwID;
  BOOL                     bCallTransfer;
  RILADDRESS               raAddress;
  RILPARTICIPANTOPERATION  dwParticipantOp;
  DWORD                    dwSIPStatus;
} RILCONFPARTICIPANTSTATUS, RILCONFPARTICIPANTSTATUS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwID


### -field bCallTransfer


### -field raAddress


### -field dwParticipantOp


### -field dwSIPStatus


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