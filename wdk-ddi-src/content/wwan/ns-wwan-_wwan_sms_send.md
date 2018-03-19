---
UID: NS:wwan._WWAN_SMS_SEND
title: "_WWAN_SMS_SEND"
author: windows-driver-content
description: The WWAN_SMS_SEND structure represents an SMS text message to send.
old-location: netvista\wwan_sms_send.htm
old-project: netvista
ms.assetid: 2d2e5d13-56ca-452c-86fd-4a48b11d53ab
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_SMS_SEND, PWWAN_SMS_SEND, PWWAN_SMS_SEND structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_SEND, WWAN_SMS_SEND structure [Network Drivers Starting with Windows Vista], WwanRef_5212cb88-8eeb-4aef-8ecd-8a0634db962c.xml, _WWAN_SMS_SEND, netvista.wwan_sms_send, wwan/PWWAN_SMS_SEND, wwan/WWAN_SMS_SEND"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_SMS_SEND
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_SEND, *PWWAN_SMS_SEND
req.product: Windows 10 or later.
---

# _WWAN_SMS_SEND structure
The WWAN_SMS_SEND structure represents an SMS text message to send.

## Syntax
````
typedef struct _WWAN_SMS_SEND {
  WWAN_SMS_FORMAT SmsFormat;
  union {
    WWAN_SMS_SEND_PDU  Pdu;
    WWAN_SMS_SEND_CDMA Cdma;
  } u;
} WWAN_SMS_SEND, *PWWAN_SMS_SEND;
````

## Members


`SmsFormat`

The format of the SMS text message.

`u`

Container union for the different SMS formats.



#### Pdu

Short message data types to be used depending on the value of 
      <b>SmsFormat</b> as shown in the following table.
      

<table>
<tr>
<th>SmsFormat</th>
<th>Member to use</th>
</tr>
<tr>
<td>
WwanSmsFormatPdu

</td>
<td>
Pdu

</td>
</tr>
<tr>
<td>
WwanSmsFormatCdma

</td>
<td>
Cdma

</td>
</tr>
</table>
 



#### Cdma

Short message data types to be used depending on the value of 
      <b>SmsFormat</b> as shown in the following table.
      

<table>
<tr>
<th>SmsFormat</th>
<th>Member to use</th>
</tr>
<tr>
<td>
WwanSmsFormatPdu

</td>
<td>
Pdu

</td>
</tr>
<tr>
<td>
WwanSmsFormatCdma

</td>
<td>
Cdma

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_sms_send_cdma.md">WWAN_SMS_SEND_CDMA</a>



<a href="..\wwan\ns-wwan-_wwan_sms_send_pdu.md">WWAN_SMS_SEND_PDU</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_sms_send.md">NDIS_WWAN_SMS_SEND</a>