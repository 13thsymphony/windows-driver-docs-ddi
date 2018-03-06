---
UID: NS:wwan._WWAN_SMS_READ
title: "_WWAN_SMS_READ"
author: windows-driver-content
description: The WWAN_SMS_READ structure represents the format and filter of SMS messages to read.
old-location: netvista\wwan_sms_read.htm
old-project: netvista
ms.assetid: 920ca041-7fc8-4c6b-bc1a-7bf41dffcf7b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWWAN_SMS_READ, PWWAN_SMS_READ, PWWAN_SMS_READ structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_READ, WWAN_SMS_READ structure [Network Drivers Starting with Windows Vista], WwanRef_8b221a53-0311-4ed7-a98b-e8677cb40051.xml, _WWAN_SMS_READ, netvista.wwan_sms_read, wwan/PWWAN_SMS_READ, wwan/WWAN_SMS_READ"
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
-	WWAN_SMS_READ
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_READ, *PWWAN_SMS_READ
req.product: Windows 10 or later.
---

# _WWAN_SMS_READ structure
The WWAN_SMS_READ structure represents the format and filter of SMS messages to read.

## Syntax
````
typedef struct _WWAN_SMS_READ {
  WWAN_SMS_FORMAT SmsFormat;
  WWAN_SMS_FILTER ReadFilter;
} WWAN_SMS_READ, *PWWAN_SMS_READ;
````

## Members


`ReadFilter`

Represents the filter upon which the miniport driver should retrieve the messages. For example,
     the filter could indicate to return all messages in the index based on the message store, or all
     messages based on 
     <b>new</b>, 
     <b>old</b>, 
     <b>draft</b>, or 
     <b>sent</b> flags.

`SmsFormat`

The format in which the miniport driver should return messages for 
     <i>query</i> requests. The MB Service specifies this value.
     

<b>WwanSmsFormatCdma</b> applies only to CDMA-based devices. CDMA-based devices support only the 
     <b>WwanSmsFormatCdma</b> format.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_sms_filter.md">WWAN_SMS_FILTER</a>



<a href="..\wwan\ne-wwan-_wwan_sms_format.md">WWAN_SMS_FORMAT</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_sms_read.md">NDIS_WWAN_SMS_READ</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_READ structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>