---
UID: NS:wwan._WWAN_CONTEXT
title: "_WWAN_CONTEXT"
author: windows-driver-content
description: The WWAN_CONTEXT structure represents a provisioned context that is supported by the MB device.
old-location: netvista\wwan_context.htm
old-project: netvista
ms.assetid: 81687237-7b24-439f-b706-e0bf95b4de68
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WWAN_CONTEXT, WWAN_CONTEXT structure [Network Drivers Starting with Windows Vista], WwanRef_6700da85-2a7a-4712-86e8-fb40e11e42a1.xml, netvista.wwan_context, *PWWAN_CONTEXT, _WWAN_CONTEXT, PWWAN_CONTEXT, PWWAN_CONTEXT structure pointer [Network Drivers Starting with Windows Vista], wwan/WWAN_CONTEXT, wwan/PWWAN_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PWWAN_CONTEXT, WWAN_CONTEXT"
req.product: Windows 10 or later.
---

# _WWAN_CONTEXT structure
The WWAN_CONTEXT structure represents a provisioned context that is supported by the MB
  device.

## Syntax
````
typedef struct _WWAN_CONTEXT {
  ULONG              ContextId;
  WWAN_CONTEXT_TYPE  ContextType;
  WCHAR              AccessString[WWAN_ACCESSSTRING_LEN];
  WCHAR              UserName[WWAN_USERNAME_LEN];
  WCHAR              Password[WWAN_PASSWORD_LEN];
  WWAN_COMPRESSION   Compression;
  WWAN_AUTH_PROTOCOL AuthType;
} WWAN_CONTEXT, *PWWAN_CONTEXT;
````

## Members


`AccessString`

A NULL-terminated string to access the network. For GSM-based networks, this would be an Access
     Point Name (APN) string such as "data.thephone-company.com". For CDMA-based networks, this might be a
     special dial code such as "#777" or a Network Access Identifier (NAI) such as
     "foo@thephone-company.com". This member can be <b>NULL</b>.
     

The size of the string should not exceed 100 bytes.

`AuthType`

Authentication type to use for the PDP activation.

`Compression`

Specifies the compression to be used in the data connection for header and data. This member
     applies only to GSM-based devices. The MB Service sets this member to 
     <b>WwanCompressionNone</b> for CDMA-based devices.

`ContextId`

A unique ID for this context.
     

For 
     <i>set</i> OID_WWAN_PROVISIONED_CONTEXT requests, the MB Service can set the value to
     WWAN_CONTEXT_ID_APPEND. If this value is used, the miniport driver should decide the index for storing
     the context information. WWAN_CONTEXT_ID_APPEND should never be returned in response to 
     <i>query</i> OID_WWAN_PROVISIONED_CONTEXT requests.

`ContextType`

Specifies the type of context being represented, for example, Internet connectivity, VPN (a
     connection to a corporate network), or Voice-over-IP (VOIP). Miniport drivers should specify 
     <b>WwanContextTypeNone</b> for empty or unprovisioned contexts.

`Password`

The password to use for authentication. This member can be <b>NULL</b>.

`UserName`

The username to use for authentication. This member can be <b>NULL</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ne-wwan-_wwan_auth_protocol.md">WWAN_AUTH_PROTOCOL</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_set_provisioned_context.md">
   NDIS_WWAN_SET_PROVISIONED_CONTEXT</a>



<a href="..\wwan\ne-wwan-_wwan_compression.md">WWAN_COMPRESSION</a>



<a href="..\wwan\ne-wwan-_wwan_context_type.md">WWAN_CONTEXT_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_CONTEXT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>