---
UID: NE:wditypes._WDI_ANQP_QUERY_STATUS
title: _WDI_ANQP_QUERY_STATUS
author: windows-driver-content
description: The WDI_ANQP_QUERY_STATUS enumeration defines the Access Network Query Protocol (ANQP) query status values.
old-location: netvista\wdi_anqp_query_status.htm
old-project: netvista
ms.assetid: 5EC1B41D-2A6F-43B7-9E22-8A65CF4E11CA
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_ANQP_QUERY_STATUS, WDI_ANQP_QUERY_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_ANQP_QUERY_STATUS
req.alt-loc: wditypes.hpp
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
req.typenames: WDI_ANQP_QUERY_STATUS
req.product: Windows 10 or later.
---

# _WDI_ANQP_QUERY_STATUS enumeration



## -description
The WDI_ANQP_QUERY_STATUS enumeration defines the Access Network Query Protocol (ANQP) query status values.



## -syntax

````
typedef enum _WDI_ANQP_QUERY_STATUS { 
  WDI_ANQP_QUERY_STATUS_SUCCESS                                         = 0,
  WDI_ANQP_QUERY_STATUS_FAILURE                                         = 1,
  WDI_ANQP_QUERY_STATUS_TIMED_OUT                                       = 2,
  WDI_ANQP_QUERY_STATUS_RESOURCES                                       = 3,
  WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_PROTOCOL_NOT_SUPPORTED_ON_REMOTE  = 4,
  WDI_ANQP_QUERY_STATUS_GAS_PROTOCOL_FAILURE                            = 5,
  WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_SERVER_NOT_RESPONDING             = 6,
  WDI_ANQP_QUERY_STATUS_ACCESS_ISSUES                                   = 7
} WDI_ANQP_QUERY_STATUS;
````


## -enum-fields

### -field WDI_ANQP_QUERY_STATUS_SUCCESS

Maps to SUCCESS.


### -field WDI_ANQP_QUERY_STATUS_FAILURE

The failure did not map to any of the other status codes.


### -field WDI_ANQP_QUERY_STATUS_TIMED_OUT

  Maps to GAS_QUERY_TIMEOUT. The STA timed out waiting for a GAS response.


### -field WDI_ANQP_QUERY_STATUS_RESOURCES

The operating system is unable to allocate sufficient resources to complete the request.


### -field WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_PROTOCOL_NOT_SUPPORTED_ON_REMOTE

Maps to GAS_ADVERTISEMENT_PROTOCOL_NOT_SUPPORTED. The GAS advertisement protocol is not supported on the remote device. 


### -field WDI_ANQP_QUERY_STATUS_GAS_PROTOCOL_FAILURE

Mapped for any of the following errors.

<ul>
<li>NO_OUTSTANDING_GAS_REQUEST</li>
<li>GAS_QUERY_RESPONSE_TOO_LARGE</li>
<li>TRANSMISSION_FAILURE</li>
</ul>

### -field WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_SERVER_NOT_RESPONDING

Mapped for any of the following errors.

<ul>
<li>GAS_RESPONSE_NOT_RECEIVED_FROM_SERVER</li>
<li>GAS_QUERY_TIMEOUT</li>
<li>SERVER_UNREACHABLE</li>
</ul>

### -field WDI_ANQP_QUERY_STATUS_ACCESS_ISSUES

Mapped for any of the following errors.

<ul>
<li>REJECTED_HOME_WITH_SUGGESTED_CHANGES</li>
<li>REJECTED_FOR_SSP_PERMISSIONS</li>
<li>AP does not support unauthenticated access</li>
</ul>

## -remarks
