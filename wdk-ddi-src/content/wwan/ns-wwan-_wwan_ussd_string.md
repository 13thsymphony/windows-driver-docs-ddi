---
UID: NS:wwan._WWAN_USSD_STRING
title: "_WWAN_USSD_STRING"
author: windows-driver-content
description: The WWAN_USSD_STRING structure describes an Unstructured Supplementary Service Data (USSD) string.
old-location: netvista\wwan_ussd_string.htm
old-project: netvista
ms.assetid: 9DE6CE5D-9570-4728-ACED-D6863812A3F4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wwan_ussd_string, wwan/PWWAN_USSD_STRING, WWAN_USSD_STRING, WWAN_USSD_STRING structure [Network Drivers Starting with Windows Vista], PWWAN_USSD_STRING, PWWAN_USSD_STRING structure pointer [Network Drivers Starting with Windows Vista], *PWWAN_USSD_STRING, wwan/WWAN_USSD_STRING, _WWAN_USSD_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	WWAN_USSD_STRING
product: Windows
targetos: Windows
req.typenames: "*PWWAN_USSD_STRING, WWAN_USSD_STRING"
req.product: Windows 10 or later.
---

# _WWAN_USSD_STRING structure
The WWAN_USSD_STRING structure describes an Unstructured Supplementary Service Data (USSD) string.

## Syntax
````
typedef struct _WWAN_USSD_STRING {
  BYTE DataCodingScheme;
  BYTE StringLength;
  BYTE String[WWAN_USSD_STRING_LEN_MAX];
} WWAN_USSD_STRING, *PWWAN_USSD_STRING;
````

## Members


`DataCodingScheme`

The data coding scheme that specifies how the <b>String</b> member is encoded, as defined in 3GPP TS 23.038, section 5.

`String`



`StringLength`

The length, in bytes, of USSD string in stored in the <b>String</b> member.

## Remarks
<b>StringLength</b> can be from 1 to 160 bytes. Specify 0 bytes to indicate an absent USSD string.

This structure is designed for USSD Stage 2 (3GPP 23.090) and eliminates the need to perform any interpretation of the USSD string in the miniport driver or MB device. If the miniport driver or MB device supports USSD Stage 1 and the network uses USSD Stage 1 then the miniport driver or MB device must transcode between ASCII (IA5) used in USSD Stage 1 and this structure:

For USSD requests, the miniport driver or MB device must decode the USSD string from the GSM-7 bit default alphabet used at requests to ASCII.

For USSD notifications, the miniport driver or MB device must encode the USSD string from ASCII to GSM-7 bit and set the <b>DataCodingScheme</b> member to indicate that the GSM-7 bit default alphabet is used.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_ussd_request.md">WWAN_USSD_REQUEST</a>

<a href="..\wwan\ns-wwan-_wwan_ussd_event.md">WWAN_USSD_EVENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_USSD_STRING structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>