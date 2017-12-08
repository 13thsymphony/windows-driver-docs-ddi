---
UID: NS.WWAN._WWAN_USSD_STRING
title: _WWAN_USSD_STRING
author: windows-driver-content
description: The WWAN_USSD_STRING structure describes an Unstructured Supplementary Service Data (USSD) string.
old-location: netvista\wwan_ussd_string.htm
old-project: netvista
ms.assetid: 9DE6CE5D-9570-4728-ACED-D6863812A3F4
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WWAN_USSD_STRING, WWAN_USSD_STRING, *PWWAN_USSD_STRING
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
req.alt-api: WWAN_USSD_STRING
req.alt-loc: wwan.h
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
req.product: Windows 10 or later.
---

# _WWAN_USSD_STRING structure



## -description
The WWAN_USSD_STRING structure describes an Unstructured Supplementary Service Data (USSD) string.


## -syntax

````
typedef struct _WWAN_USSD_STRING {
  BYTE DataCodingScheme;
  BYTE StringLength;
  BYTE String[WWAN_USSD_STRING_LEN_MAX];
} WWAN_USSD_STRING, *PWWAN_USSD_STRING;
````


## -struct-fields

### -field DataCodingScheme

The data coding scheme that specifies how the <b>String</b> member is encoded, as defined in 3GPP TS 23.038, section 5.

### -field StringLength

The length, in bytes, of USSD string in stored in the <b>String</b> member.

### -field String[WWAN_USSD_STRING_LEN_MAX]

The USSD string encoded according to the <b>DataCodingScheme</b> member.

## -remarks
<b>StringLength</b> can be from 1 to 160 bytes. Specify 0 bytes to indicate an absent USSD string.

This structure is designed for USSD Stage 2 (3GPP 23.090) and eliminates the need to perform any interpretation of the USSD string in the miniport driver or MB device. If the miniport driver or MB device supports USSD Stage 1 and the network uses USSD Stage 1 then the miniport driver or MB device must transcode between ASCII (IA5) used in USSD Stage 1 and this structure:

For USSD requests, the miniport driver or MB device must decode the USSD string from the GSM-7 bit default alphabet used at requests to ASCII.

For USSD notifications, the miniport driver or MB device must encode the USSD string from ASCII to GSM-7 bit and set the <b>DataCodingScheme</b> member to indicate that the GSM-7 bit default alphabet is used.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported starting with  Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_ussd_request">WWAN_USSD_REQUEST</a>
</dt>
<dt>
<a href="netvista.wwan_ussd_event">WWAN_USSD_EVENT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_USSD_STRING structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
