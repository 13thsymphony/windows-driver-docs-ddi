---
UID: NE:wwan._WWAN_AUTH_PROTOCOL
title: "_WWAN_AUTH_PROTOCOL"
author: windows-driver-content
description: The WWAN_AUTH_PROTOCOL enumeration lists the different types of authentication protocols that are supported by the MB device.
old-location: netvista\wwan_auth_protocol.htm
old-project: netvista
ms.assetid: 33c9523e-3195-456f-8e17-b9539475bc67
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWWAN_AUTH_PROTOCOL, PWWAN_AUTH_PROTOCOL, PWWAN_AUTH_PROTOCOL enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_PROTOCOL, WWAN_AUTH_PROTOCOL enumeration [Network Drivers Starting with Windows Vista], WwanAuthProtocolChap, WwanAuthProtocolMax, WwanAuthProtocolMsChapV2, WwanAuthProtocolNone, WwanAuthProtocolPap, WwanRef_b7f5b77c-f85f-4ed2-adfa-306b903da5fd.xml, _WWAN_AUTH_PROTOCOL, netvista.wwan_auth_protocol, wwan/PWWAN_AUTH_PROTOCOL, wwan/WWAN_AUTH_PROTOCOL, wwan/WwanAuthProtocolChap, wwan/WwanAuthProtocolMax, wwan/WwanAuthProtocolMsChapV2, wwan/WwanAuthProtocolNone, wwan/WwanAuthProtocolPap"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 7.
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
-	WWAN_AUTH_PROTOCOL
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_PROTOCOL, *PWWAN_AUTH_PROTOCOL
req.product: Windows 10 or later.
---

# _WWAN_AUTH_PROTOCOL Enumeration
The WWAN_AUTH_PROTOCOL enumeration lists the different types of authentication protocols that are
  supported by the MB device.

## Syntax
````
typedef enum _WWAN_AUTH_PROTOCOL { 
  WwanAuthProtocolNone      = 0,
  WwanAuthProtocolPap,
  WwanAuthProtocolChap,
  WwanAuthProtocolMsChapV2,
  WwanAuthProtocolMax
} WWAN_AUTH_PROTOCOL, *PWWAN_AUTH_PROTOCOL;
````

## Constants

<table>
            
                <tr>
                    <td>WwanAuthProtocolAuto</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WwanAuthProtocolChap</td>
                    <td>Use the Challenge Handshake Authentication Protocol (CHAP).</td>
                </tr>
            
                <tr>
                    <td>WwanAuthProtocolMax</td>
                    <td>The total number of supported authentication protocols.</td>
                </tr>
            
                <tr>
                    <td>WwanAuthProtocolMsChapV2</td>
                    <td>Use the Microsoft Challenge Handshake Authentication Protocol (CHAP) v2.0.</td>
                </tr>
            
                <tr>
                    <td>WwanAuthProtocolNone</td>
                    <td>No authentication protocol.</td>
                </tr>
            
                <tr>
                    <td>WwanAuthProtocolPap</td>
                    <td>Unencrypted password authentication.</td>
                </tr>
</table>

## Remarks

This enumeration applies only to GSM devices. The MB Service specifies 
    <b>WwanAuthProtocolNone</b> as the authentication type for CDMA-based devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7. Available starting with Windows 7. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_context.md">WWAN_CONTEXT</a>



<a href="..\wwan\ns-wwan-_wwan_set_context_state.md">WWAN_SET_CONTEXT_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_PROTOCOL enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>