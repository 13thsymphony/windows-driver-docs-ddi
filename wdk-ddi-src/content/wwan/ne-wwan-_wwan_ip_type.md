---
UID: NE:wwan._WWAN_IP_TYPE
title: "_WWAN_IP_TYPE"
author: windows-driver-content
description: The WWAN_IP_TYPE enumeration lists the different levels of supported IP.
old-location: netvista\wwan_ip_type.htm
old-project: netvista
ms.assetid: E4CE7BE7-021A-4C9A-B467-B63AACEC1266
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
product: Windows
targetos: Windows
req.typenames: WWAN_IP_TYPE, *PWWAN_IP_TYPE
req.product: Windows 10 or later.
---

# _WWAN_IP_TYPE Enumeration
The WWAN_IP_TYPE enumeration lists the different levels of supported IP.

## Syntax
````
typedef enum _WWAN_IP_TYPE { 
  WwanIPTypeDefault  = 0,
  WwanIPTypeIPv4     = ,
  WwanIPTypeIPv6     = ,
  WwanIPTypeIpv4v6   = 
} WWAN_IP_TYPE;
````

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
                    <td>WwanIPTypeIpv4v6</td>
                    <td>IPv4 with IPv6</td>
                </tr>
            
                <tr>
                    <td>WwanIPTypeIPv6</td>
                    <td>IPv6</td>
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

<a href="..\wwan\ns-wwan-_wwan_context_state.md">WWAN_CONTEXT_STATE</a>



<a href="..\wwan\ns-wwan-_wwan_set_context_state.md">WWAN_SET_CONTEXT_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_IP_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>