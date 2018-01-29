---
UID : NS:windot11._DOT11_WFD_GO_INTENT
title : _DOT11_WFD_GO_INTENT
author : windows-driver-content
description : The DOT11_WFD_GO_INTENT structure represents the Group Intent value used during Group Owner Negotiation
old-location : netvista\_dot11_wfd_go_intent.htm
old-project : netvista
ms.assetid : 8E4F88EF-04A9-4313-AE6A-2467DA08044A
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : windot11/DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT, windot11/PDOT11_WFD_GO_INTENT, PDOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT, _DOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_GO_INTENT structure pointer [Network Drivers Starting with Windows Vista], netvista._dot11_wfd_go_intent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Windot11.h
req.target-type : Windows
req.target-min-winverclnt : Supported in Windows 8
req.target-min-winversvr : 
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
req.typenames : DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT
req.product : Windows 10 or later.
---

# _DOT11_WFD_GO_INTENT structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_GO_INTENT</b> structure represents the Group Intent value used during Group Owner Negotiation

## Syntax
````
typedef struct _DOT11_WFD_GO_INTENT {
  UCHAR TieBreaker:1;
  UCHAR Intent:7;
} DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT;
````

## Members


`Intent`



`TieBreaker`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Windot11.h) |