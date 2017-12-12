---
UID: NS.WWAN._WWAN_SET_SIGNAL_INDICATION
title: _WWAN_SET_SIGNAL_INDICATION
author: windows-driver-content
description: The WWAN_SET_SIGNAL_INDICATION structure represents the frequency of RSSI interval and RSSI threshold notifications.
old-location: netvista\wwan_set_signal_indication.htm
old-project: netvista
ms.assetid: 266ec8f5-f6ec-47e5-b433-4f570f2d43d2
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_SET_SIGNAL_INDICATION, WWAN_SET_SIGNAL_INDICATION, *PWWAN_SET_SIGNAL_INDICATION
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
req.alt-api: WWAN_SET_SIGNAL_INDICATION
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

# _WWAN_SET_SIGNAL_INDICATION structure



## -description
The WWAN_SET_SIGNAL_INDICATION structure represents the frequency of RSSI interval and RSSI threshold
  notifications.



## -syntax

````
typedef struct _WWAN_SET_SIGNAL_INDICATION {
  ULONG RssiInterval;
  ULONG RssiThreshold;
} WWAN_SET_SIGNAL_INDICATION, *PWWAN_SET_SIGNAL_INDICATION;
````


## -struct-fields

### -field RssiInterval

The RSSI interval, in seconds.


### -field RssiThreshold

The RSSI threshold, in threshold units.


## -remarks
To minimize power consumption, the MB Service specifies a default interval and a default threshold for
    sending notifications that are based on an RSSI value that changes. In some situations, such as during
    long periods of user inactivity (in the case of the default interval), or in areas that have a strong
    signal (in the case of a default threshold), this value specifies when a longer interval or threshold (as
    appropriate) may be used to conserve additional power. However, miniport drivers are not required to
    adhere to an increased interval or threshold.

The WWAN_RSSI_DEFAULT value indicates that no suggested interval value is available, and that the
    miniport driver should use the default minimum interval or the default threshold (as appropriate). A
    value of WWAN_RSSI_DISABLE that the miniport driver will stop reporting the signal state based on the
    interval or threshold limit (as appropriate).

The miniport driver can always switch to its device-specific default reporting interval if the request
    in this member is outside of device limits.


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
<a href="netvista.ndis_wwan_set_signal_indication">
   NDIS_WWAN_SET_SIGNAL_INDICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SET_SIGNAL_INDICATION structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

