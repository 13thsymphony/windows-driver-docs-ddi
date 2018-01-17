---
UID: NE:wwan._WWAN_PIN_TYPE
title: _WWAN_PIN_TYPE
author: windows-driver-content
description: The WWAN_PIN_TYPE enumeration lists the different types of Personal Identification Numbers (PINs) that are supported by the MB device.
old-location: netvista\wwan_pin_type.htm
old-project: netvista
ms.assetid: f6b8146e-dbe2-4c73-beb2-02868db9fb27
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_PIN_TYPE, WWAN_PIN_TYPE, *PWWAN_PIN_TYPE
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
req.alt-api: WWAN_PIN_TYPE
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
req.typenames: WWAN_PIN_TYPE, *PWWAN_PIN_TYPE
req.product: Windows 10 or later.
---

# _WWAN_PIN_TYPE enumeration



## -description
The WWAN_PIN_TYPE enumeration lists the different types of Personal Identification Numbers (PINs)
  that are supported by the MB device.



## -syntax

````
typedef enum _WWAN_PIN_TYPE { 
  WwanPinTypeNone               = 0,
  WwanPinTypeCustom,
  WwanPinTypePin1,
  WwanPinTypePin2,
  WwanPinTypeDeviceSimPin,
  WwanPinTypeDeviceFirstSimPin,
  WwanPinTypeNetworkPin,
  WwanPinTypeNetworkSubsetPin,
  WwanPinTypeSvcProviderPin,
  WwanPinTypeCorporatePin,
  WwanPinTypeSubsidyLock,
  WwanPinTypePuk1,
  WwanPinTypePuk2,
  WwanPinTypeDeviceFirstSimPuk,
  WwanPinTypeNetworkPuk,
  WwanPinTypeNetworkSubsetPuk,
  WwanPinTypeSvcProviderPuk,
  WwanPinTypeCorporatePuk,
  WwanPinTypeMax
} WWAN_PIN_TYPE, *PWWAN_PIN_TYPE;
````


## -enum-fields

### -field WwanPinTypeNone

No PIN is pending to be entered.


### -field WwanPinTypeCustom

The PIN type is a custom type and is none of the other PIN types listed in this
     enumeration.


### -field WwanPinTypePin1

The PIN1 key.


### -field WwanPinTypePin2

The PIN2 key.


### -field WwanPinTypeDeviceSimPin

The device to SIM key.


### -field WwanPinTypeDeviceFirstSimPin

The device to very first SIM key.


### -field WwanPinTypeNetworkPin

The network personalization key.


### -field WwanPinTypeNetworkSubsetPin

The network subset personalization key.


### -field WwanPinTypeSvcProviderPin

The service provider (SP) personalization key.


### -field WwanPinTypeCorporatePin

The corporate personalization key.


### -field WwanPinTypeSubsidyLock

The subsidy unlock key.


### -field WwanPinTypePuk1

The Personal Identification Number1 Unlock Key (PUK1).


### -field WwanPinTypePuk2

The Personal Identification Number2 Unlock Key (PUK2).


### -field WwanPinTypeDeviceFirstSimPuk

The device to very first SIM PIN unlock key.


### -field WwanPinTypeNetworkPuk

The network personalization unlock key.


### -field WwanPinTypeNetworkSubsetPuk

The network subset personalization unlock key.


### -field WwanPinTypeSvcProviderPuk

The service provider (SP) personalization unlock key.


### -field WwanPinTypeCorporatePuk

The corporate personalization unlock key.


### -field WwanPinTypeMax

The total number of supported PIN types.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_pin_info.md">WWAN_PIN_INFO</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_pin_action.md">WWAN_PIN_ACTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

