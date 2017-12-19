---
UID: NE.wwan._WWAN_SMS_CDMA_LANG
title: _WWAN_SMS_CDMA_LANG
author: windows-driver-content
description: The WWAN_SMS_CDMA_LANG enumeration lists the different SMS CDMA languages that are supported by the MB device.
old-location: netvista\wwan_sms_cdma_lang.htm
old-project: NetVista
ms.assetid: 5294ce07-a4eb-4c21-88f1-04889dfbc1a1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WWAN_SMS_CDMA_LANG, WWAN_SMS_CDMA_LANG, *PWWAN_SMS_CDMA_LANG, PWWAN_SMS_CDMA_LANG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_SMS_CDMA_LANG
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

# _WWAN_SMS_CDMA_LANG enumeration



## -description
The WWAN_SMS_CDMA_LANG enumeration lists the different SMS CDMA languages that are supported by the
  MB device.



## -syntax

````
typedef enum _WWAN_SMS_CDMA_LANG { 
  WwanSmsCdmaLangUnknown   = 0,
  WwanSmsCdmaLangEnglish,
  WwanSmsCdmaLangFrench,
  WwanSmsCdmaLangSpanish,
  WwanSmsCdmaLangJapanese,
  WwanSmsCdmaLangKorean,
  WwanSmsCdmaLangChinese,
  WwanSmsCdmaLangHebrew,
  WwanSmsCdmaLangMax
} WWAN_SMS_CDMA_LANG, *PWWAN_SMS_CDMA_LANG;
````


## -enum-fields

### -field WwanSmsCdmaLangUnknown

The message language is unknown.


### -field WwanSmsCdmaLangEnglish

The message is in English.


### -field WwanSmsCdmaLangFrench

The message is in French.


### -field WwanSmsCdmaLangSpanish

The message is in Spanish.


### -field WwanSmsCdmaLangJapanese

The message is in Japanese.


### -field WwanSmsCdmaLangKorean

The message is in Korean.


### -field WwanSmsCdmaLangChinese

The message is in Chinese.


### -field WwanSmsCdmaLangHebrew

The message is in Hebrew.


### -field WwanSmsCdmaLangMax

The total number of supported SMS CDMA languages.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

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
<a href="netvista.wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>
</dt>
<dt>
<a href="netvista.wwan_sms_send_cdma">WWAN_SMS_SEND_CDMA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20WWAN_SMS_CDMA_LANG enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

