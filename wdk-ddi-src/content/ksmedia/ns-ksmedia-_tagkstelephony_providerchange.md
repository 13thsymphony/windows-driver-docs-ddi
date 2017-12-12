---
UID: NS.KSMEDIA._TAGKSTELEPHONY_PROVIDERCHANGE
title: _tagKSTELEPHONY_PROVIDERCHANGE
author: windows-driver-content
description: The KSTELEPHONY_PROVIDERCHANGE structure specifies the phone call type and provider change operation to use for the KSPROPERTY_TELEPHONY_PROVIDERCHANGE property.
old-location: audio\kstelephony_providerchange.htm
old-project: audio
ms.assetid: 07928837-321C-4501-BDFF-4611BF6912F6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _tagKSTELEPHONY_PROVIDERCHANGE, *PKSTELEPHONY_PROVIDERCHANGE, KSTELEPHONY_PROVIDERCHANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSTELEPHONY_PROVIDERCHANGE
req.alt-loc: ksmedia.h
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

# _tagKSTELEPHONY_PROVIDERCHANGE structure



## -description
The <b>KSTELEPHONY_PROVIDERCHANGE</b> structure specifies the phone call type and provider change operation to use for the <a href="https://msdn.microsoft.com/library/windows/hardware/mt169876">KSPROPERTY_TELEPHONY_PROVIDERCHANGE</a> property.



## -syntax

````
typedef struct _tagKSTELEPHONY_PROVIDERCHANGE {
  TELEPHONY_CALLTYPE         CallType;
  TELEPHONY_PROVIDERCHANGEOP ProviderChangeOp;
} KSTELEPHONY_PROVIDERCHANGE, *PKSTELEPHONY_PROVIDERCHANGE;
````


## -struct-fields

### -field CallType

Specifies the type of phone call (circuit-switched, LTE packet-switched, or WLAN packet-switched).


### -field ProviderChangeOp

Specifies the change operation requested by the provider (begin, end, or cancel).


## -remarks
The audio stack uses the KSTELEPHONY_PROVIDERCHANGE property to indicate the start and the end of SRVCC to the audio driver. This property communicates the call type (LTE packet-switched, WLAN packet-switched, or circuit-switched) and the provider change operation (begin, end, or cancel) to driver. The call type is ignored when the provider operation is for ending the SRVCC. 

When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_BEGIN, the driver updates that provider’s call state to TELEPHONY_CALLSTATE_PROVIDERTRANSITION. When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_END, the driver updates that provider’s call state to TELEPHONY_CALLSTATE_ENABLED. During SRVCC, the driver must continue to use the associated KSNODETYPE_TELEPHONY_BIDI endpoint, and it does not change the jack states of this endpoint. When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_CANCEL, SRVCC is being canceled, and the driver should revert back to a pre-SRVCC call.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Client

</th>
<td width="70%">
Windows 10 Mobile

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>