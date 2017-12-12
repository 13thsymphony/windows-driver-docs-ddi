---
UID: NS.WWAN._WWAN_PROVIDER
title: _WWAN_PROVIDER
author: windows-driver-content
description: The WWAN_PROVIDER structure represents details about a network provider.
old-location: netvista\wwan_provider.htm
old-project: netvista
ms.assetid: 2bca3123-3ac4-44fe-8d47-051314ef3cb7
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_PROVIDER, *PWWAN_PROVIDER, WWAN_PROVIDER
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
req.alt-api: WWAN_PROVIDER
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

# _WWAN_PROVIDER structure



## -description
The WWAN_PROVIDER structure represents details about a network provider.



## -syntax

````
typedef struct _WWAN_PROVIDER {
  WCHAR ProviderId[WWAN_PROVIDERID_LEN];
  ULONG ProviderState;
  WCHAR ProviderName[WWAN_PROVIDERNAME_LEN];
  ULONG WwanDataClass;
} WWAN_PROVIDER, *PWWAN_PROVIDER;
````


## -struct-fields

### -field ProviderId

A NULL-terminated numeric (0-9) string that represents the network provider identity.
     

For GSM-based networks, this string is a concatenation of a three-digit Mobile Country Code (MCC) and
     a two or three-digit Mobile Network Code (MNC). GSM-based carriers may have more than one MNC, and hence
     more than one 
     <b>ProviderId</b> .

For CDMA-based networks, this string is a five-digit System ID (SID). Generally a CDMA-based carrier
     has more than one SID. Typically, the carrier has one SID for each market, which is usually divided
     geographically within a nation by regulations, such as Metropolitan Statistical Areas (MSA) in the
     United States of America. Miniport drivers of CDMA-based devices must specify
     WWAN_CDMA_DEFAULT_PROVIDER_ID if this information is not available.


### -field ProviderState

A value that represents the various states that the network provider's entry can be tagged with.
     The following table shows the possible values that miniport drivers should specify (one or more values
     can be specified).
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_HOME

</td>
<td>
The network provider is the home operator.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_FORBIDDEN

</td>
<td>
The network provider is on the forbidden list.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_PREFERRED

</td>
<td>
The network provider is on the preferred list.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_VISIBLE

</td>
<td>
The network provider is visible.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_REGISTERED

</td>
<td>
The network provider is currently registered by the device.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_UNKNOWN

</td>
<td>
The network provider state is unknown.

</td>
</tr>
</table>
 

Some values in the previous table apply only to specific object identifiers (OIDs). The following
     table shows the associations between those values and related OIDs.

<table>
<tr>
<th>Value</th>
<th>OID</th>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_HOME

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569826">OID_WWAN_HOME_PROVIDER</a>


</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_FORBIDDEN

WWAN_PROVIDER_STATE_PREFERRED

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a>


</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_VISIBLE

WWAN_PROVIDER_STATE_REGISTERED

WWAN_PROVIDER_STATE_HOME

WWAN_PROVIDER_STATE_PREFERRED

WWAN_PROVIDER_STATE_FORBIDDEN

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a>


</td>
</tr>
</table>
 


### -field ProviderName

A NULL-terminated string that represents the network provider's name. This member is limited to,
     at most, WWAN_PROVIDERNAME_LEN characters.
     

For GSM-based networks, if the Preferred Presentation of Country Initials and Mobile Network Name
     (PPCI&amp;N) is longer than WWAN_PROVIDERNAME_LEN characters, the miniport driver should abbreviate the
     network name.

This member is ignored when the MB Service sets the preferred provider list.

Miniport drivers should specify a <b>NULL</b> string for devices that do not have this
     information.


### -field WwanDataClass

A bitmap that represents the data-class(es) that the device supports. For a detailed list of
     values, see the 
     <b>WwanDataClass</b> member of 
     <a href="netvista.wwan_device_caps">WWAN_DEVICE_CAPS</a>.
     

This member can be ignored when queried for OID_WWAN_HOME_PROVIDER.


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
<a href="netvista.ndis_wwan_home_provider">NDIS_WWAN_HOME_PROVIDER</a>
</dt>
<dt>
<a href="netvista.ndis_wwan_preferred_providers">NDIS_WWAN_PREFERRED_PROVIDERS</a>
</dt>
<dt>
<a href="netvista.ndis_wwan_visible_providers">NDIS_WWAN_VISIBLE_PROVIDERS</a>
</dt>
<dt>
<a href="netvista.wwan_device_caps">WWAN_DEVICE_CAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PROVIDER structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

