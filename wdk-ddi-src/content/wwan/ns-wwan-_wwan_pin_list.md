---
UID: NS.WWAN._WWAN_PIN_LIST
title: _WWAN_PIN_LIST
author: windows-driver-content
description: The WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers (PINs).
old-location: netvista\wwan_pin_list.htm
old-project: netvista
ms.assetid: 7ddea69c-db40-4fae-9ca9-5eadc9b40b0c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_PIN_LIST, *PWWAN_PIN_LIST, WWAN_PIN_LIST
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
req.alt-api: WWAN_PIN_LIST
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

# _WWAN_PIN_LIST structure



## -description
The WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers
  (PINs).



## -syntax

````
typedef struct _WWAN_PIN_LIST {
  WWAN_PIN_DESC WwanPinDescPin1;
  WWAN_PIN_DESC WwanPinDescPin2;
  WWAN_PIN_DESC WwanPinDescDeviceSimPin;
  WWAN_PIN_DESC WwanPinDescDeviceFirstSimPin;
  WWAN_PIN_DESC WwanPinDescNetworkPin;
  WWAN_PIN_DESC WwanPinDescNetworkSubsetPin;
  WWAN_PIN_DESC WwanPinDescSvcProviderPin;
  WWAN_PIN_DESC WwanPinDescCorporatePin;
  WWAN_PIN_DESC WwanPinDescSubsidyLock;
  WWAN_PIN_DESC WwanPinDescCustom;
} WWAN_PIN_LIST, *PWWAN_PIN_LIST;
````


## -struct-fields

### -field WwanPinDescPin1

Description for PIN1. For GSM-based devices, this is a Subscriber Identity Module (SIM) PIN. For
     CDMA-based devices, power-on device lock is reported as PIN1.


### -field WwanPinDescPin2

Description for PIN2. This is a SIM PIN2 that protects certain SIM functionality.


### -field WwanPinDescDeviceSimPin

Description for the device-to-SIM-card PIN. This is a PIN that locks the device to a specific
     SIM.


### -field WwanPinDescDeviceFirstSimPin

Description for the device-to-very-first-SIM-card PIN. This is a PIN that locks the device to the
     very first inserted SIM.


### -field WwanPinDescNetworkPin

Description for the network personalization PIN. This is a PIN that allows the device to be
     personalized to a network. For more information about this PIN type, see section 22.022 of the 3GPP
     specification.


### -field WwanPinDescNetworkSubsetPin

Description for network subset personalization PIN. This is a PIN that allows the device to be
     personalized to a subset of a network. For more information about this PIN type, see section 22.022 of
     the 3GPP specification.


### -field WwanPinDescSvcProviderPin

Description for Service Provider (SP) personalization PIN. This is a PIN that allows the device to
     be personalized to a service provider. For more information about this PIN type, see section 22.022 of
     the 3GPP specification.


### -field WwanPinDescCorporatePin

Description for corporate personalization PIN. This is a PIN that allows the device to be
     personalized to a specific company. For more information about this PIN type, see section 22.022 of the
     3GPP specification.


### -field WwanPinDescSubsidyLock

Description for subsidy unlock PIN. This is a PIN that allows the device to be restricted to
     operate on a specific network. For more information about this PIN type, see section 22.022 of the 3GPP
     specification.


### -field WwanPinDescCustom

Description for custom PIN. This is a custom vendor-defined PIN type. It is not included in the
     above list.


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
<a href="netvista.wwan_pin_desc">WWAN_PIN_DESC</a>
</dt>
<dt>
<a href="netvista.ndis_wwan_pin_list">NDIS_WWAN_PIN_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_LIST structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

