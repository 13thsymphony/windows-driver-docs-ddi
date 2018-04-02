---
UID: NE:wwan._WWAN_IP_TYPE
title: "_WWAN_IP_TYPE"
author: windows-driver-content
description: The WWAN_IP_TYPE enumeration lists the different levels of supported IP.
old-location: netvista\wwan_ip_type.htm
old-project: netvista
ms.assetid: E4CE7BE7-021A-4C9A-B467-B63AACEC1266
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_IP_TYPE, WWAN_IP_TYPE, WWAN_IP_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanIPTypeDefault, WwanIPTypeIPv4, WwanIPTypeIPv6, WwanIPTypeIpv4v6, _WWAN_IP_TYPE, netvista.wwan_ip_type, wwan/WWAN_IP_TYPE, wwan/WwanIPTypeDefault, wwan/WwanIPTypeIPv4, wwan/WwanIPTypeIPv6, wwan/WwanIPTypeIpv4v6"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
-	WWAN_IP_TYPE
product:
- Windows
targetos: Windows
req.typenames: WWAN_IP_TYPE, *PWWAN_IP_TYPE
req.product: Windows 10 or later.
---

# _WWAN_IP_TYPE Enumeration
The WWAN_IP_TYPE enumeration lists the different levels of supported IP.

## Syntax
```
typedef enum _WWAN_IP_TYPE {
  WwanIPTypeDefault  ,
  WwanIPTypeIPv4     ,
  WwanIPTypeIPv6     ,
  WwanIPTypeIpv4v6   ,
  WwanIPTypeXlat
} *PWWAN_IP_TYPE, WWAN_IP_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>WwanIPTypeDefault</td>
                    <td>Default IP.</td>
                </tr>
            
                <tr>
                    <td>WwanIPTypeIPv4</td>
                    <td>IPv4.</td>
                </tr>
            
                <tr>
                    <td>WwanIPTypeIPv6</td>
                    <td>IPv6</td>
                </tr>
            
                <tr>
                    <td>WwanIPTypeIpv4v6</td>
                    <td>IPv4 with IPv6</td>
                </tr>
            
                <tr>
                    <td>WwanIPTypeXlat</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows 8 and later versions of Windows. Versions:\_Supported in Windows 8 and later versions of Windows. |
| **Header** | wwan.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571202">WWAN_CONTEXT_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571235">WWAN_SET_CONTEXT_STATE</a>