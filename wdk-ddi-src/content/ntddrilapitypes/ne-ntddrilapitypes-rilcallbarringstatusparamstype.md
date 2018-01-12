---
UID: NE:ntddrilapitypes.RILCALLBARRINGSTATUSPARAMSTYPE
title: RILCALLBARRINGSTATUSPARAMSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallbarringstatusparamstype.htm
old-project: netvista
ms.assetid: 95c15362-227c-4912-9eec-a18fee92f340
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILCALLBARRINGSTATUSPARAMSTYPE, RILCALLBARRINGSTATUSPARAMSTYPE
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
req.alt-api: RILCALLBARRINGSTATUSPARAMSTYPE
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
req.typenames: RILCALLBARRINGSTATUSPARAMSTYPE
---

# RILCALLBARRINGSTATUSPARAMSTYPE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILCALLBARRINGSTATUSPARAMSTYPE { 
  RIL_BARRTYPE_OUTGOINGINT,
  RIL_BARRTYPE_OUTGOINGINTEXTOHOME,
  RIL_BARRTYPE_ALLINCOMING,
  RIL_BARRTYPE_INCOMINGROAMING,
  RIL_BARRTYPE_INCOMINGNOTINUICC,
  RIL_BARRTYPE_ALLBARRING,
  RIL_BARRTYPE_ALLOUTGOINGBARRING,
  RIL_BARRTYPE_ALLINCOMINGBARRING,
  RIL_BARRTYPE_ALL
} RILCALLBARRINGSTATUSPARAMSTYPE;
````


## -enum-fields

### -field RIL_BARRTYPE_OUTGOINGINT


### -field RIL_BARRTYPE_OUTGOINGINTEXTOHOME


### -field RIL_BARRTYPE_ALLINCOMING


### -field RIL_BARRTYPE_INCOMINGROAMING


### -field RIL_BARRTYPE_INCOMINGNOTINUICC


### -field RIL_BARRTYPE_ALLBARRING


### -field RIL_BARRTYPE_ALLOUTGOINGBARRING


### -field RIL_BARRTYPE_ALLINCOMINGBARRING


### -field RIL_BARRTYPE_ALL


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