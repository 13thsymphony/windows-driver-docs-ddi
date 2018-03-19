---
UID: NS:wwan._WWAN_IP_ADDRESS_STATE
title: "_WWAN_IP_ADDRESS_STATE"
author: windows-driver-content
description: The WWAN_IP_ADDRESS_STATE structure represents the IP addresses, gateways, DNS servers, and/or MTUs of a PDP context.
old-location: netvista\wwan_ip_address_state.htm
old-project: netvista
ms.assetid: 63D3B055-A3B0-4A76-B53C-C5E87C40A52C
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_IP_ADDRESS_STATE, PWWAN_IP_ADDRESS_STATE, PWWAN_IP_ADDRESS_STATE structure pointer [Network Drivers Starting with Windows Vista], WWAN_IP_ADDRESS_STATE, WWAN_IP_ADDRESS_STATE structure [Network Drivers Starting with Windows Vista], _WWAN_IP_ADDRESS_STATE, netvista.wwan_ip_address_state, wwan/PWWAN_IP_ADDRESS_STATE, wwan/WWAN_IP_ADDRESS_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_IP_ADDRESS_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_IP_ADDRESS_STATE, *PWWAN_IP_ADDRESS_STATE
req.product: Windows 10 or later.
---

# _WWAN_IP_ADDRESS_STATE structure
The WWAN_IP_ADDRESS_STATE structure represents the IP addresses, gateways, DNS servers, and/or MTUs of a PDP context.

## Syntax
````
typedef struct _WWAN_IP_ADDRESS_STATE {
  WWAN_IP_CONFIGURATION_FLAGS IPv4Flags;
  WWAN_IP_CONFIGURATION_FLAGS IPv6Flags;
  ULONG                       IPv4MTU;
  ULONG                       IPv6MTU;
  PWWAN_IPADDRESS_ENTRY       IpTable;
  ULONG                       IpCount;
  PWWAN_IPADDRESS_ENTRY       GatewayTable;
  ULONG                       GatewayCount;
  PWWAN_IPADDRESS_ENTRY       DnsTable;
  ULONG                       DnsCount;
} WWAN_IP_ADDRESS_STATE, *PWWAN_IP_ADDRESS_STATE;
````

## Members


`IPv4Flags`

Flags that describe  the availability of the IPV4 address, gateway, DNS server, and MTU information of the PDP context.

`IPv6Flags`

Flags that describe the availability of the IPV6 address, gateway, DNS server, and MTU information of the PDP context.

`IPv4MTU`

The IPV4 MTU value of the PDP context.

`IPv6MTU`

The IPV6 MTU value of the PDP context.

`IpTable`

Pointer to the start of an array of IP addresses of the PDP context.

`IpCount`

The number of entries in the <b>IpTable</b> array.

`GatewayTable`

Pointer to the start of an array of gateways of the PDP context.

`GatewayCount`

The number of entries in the <b>GatewayTable</b> array.

`DnsTable`

Pointer to the start of an array of DNS servers of the PDP context.

`DnsCount`

The number of entries in the <b>DnsTable</b> array.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 8.1 and later versions of Windows. Available in Windows 8.1 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_ipaddress_entry.md">WWAN_IPADDRESS_ENTRY</a>



<a href="..\wwan\ns-wwan-wwan_ip_configuration_flags.md">WWAN_IP_CONFIGURATION_FLAGS</a>