---
UID : NS:ksmedia._tagKSTELEPHONY_PROVIDERCHANGE
title : _tagKSTELEPHONY_PROVIDERCHANGE
author : windows-driver-content
description : The KSTELEPHONY_PROVIDERCHANGE structure specifies the phone call type and provider change operation to use for the KSPROPERTY_TELEPHONY_PROVIDERCHANGE property.
old-location : audio\kstelephony_providerchange.htm
old-project : audio
ms.assetid : 07928837-321C-4501-BDFF-4611BF6912F6
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PKSTELEPHONY_PROVIDERCHANGE structure pointer [Audio Devices], *PKSTELEPHONY_PROVIDERCHANGE, ksmedia/KSTELEPHONY_PROVIDERCHANGE, audio.kstelephony_providerchange, KSTELEPHONY_PROVIDERCHANGE structure [Audio Devices], _tagKSTELEPHONY_PROVIDERCHANGE, ksmedia/PKSTELEPHONY_PROVIDERCHANGE, KSTELEPHONY_PROVIDERCHANGE, PKSTELEPHONY_PROVIDERCHANGE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10,Windows 10 Mobile
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSTELEPHONY_PROVIDERCHANGE, *PKSTELEPHONY_PROVIDERCHANGE
---

# _tagKSTELEPHONY_PROVIDERCHANGE structure
The <b>KSTELEPHONY_PROVIDERCHANGE</b> structure specifies the phone call type and provider change operation to use for the <a href="https://msdn.microsoft.com/library/windows/hardware/mt169876">KSPROPERTY_TELEPHONY_PROVIDERCHANGE</a> property.

## Syntax
````
typedef struct _tagKSTELEPHONY_PROVIDERCHANGE {
  TELEPHONY_CALLTYPE         CallType;
  TELEPHONY_PROVIDERCHANGEOP ProviderChangeOp;
} KSTELEPHONY_PROVIDERCHANGE, *PKSTELEPHONY_PROVIDERCHANGE;
````

## Members


`CallType`

Specifies the type of phone call (circuit-switched, LTE packet-switched, or WLAN packet-switched).

`ProviderChangeOp`

Specifies the change operation requested by the provider (begin, end, or cancel).

## Remarks
The audio stack uses the KSTELEPHONY_PROVIDERCHANGE property to indicate the start and the end of SRVCC to the audio driver. This property communicates the call type (LTE packet-switched, WLAN packet-switched, or circuit-switched) and the provider change operation (begin, end, or cancel) to driver. The call type is ignored when the provider operation is for ending the SRVCC. 

When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_BEGIN, the driver updates that provider’s call state to TELEPHONY_CALLSTATE_PROVIDERTRANSITION. When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_END, the driver updates that provider’s call state to TELEPHONY_CALLSTATE_ENABLED. During SRVCC, the driver must continue to use the associated KSNODETYPE_TELEPHONY_BIDI endpoint, and it does not change the jack states of this endpoint. When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_CANCEL, SRVCC is being canceled, and the driver should revert back to a pre-SRVCC call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |