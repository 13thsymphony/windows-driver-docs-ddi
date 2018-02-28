---
UID: NC:wlanihv.DOT11EXT_SET_EXCLUDE_UNENCRYPTED
title: DOT11EXT_SET_EXCLUDE_UNENCRYPTED
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetexcludeunencrypted.htm
old-project: netvista
ms.assetid: b6482124-0d65-4953-8a8f-a09c0a88d830
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_SET_EXCLUDE_UNENCRYPTED, Dot11ExtSetExcludeUnencrypted, Dot11ExtSetExcludeUnencrypted callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_aa6f594d-e5b7-4ba0-9ad8-deb42f6c23ad.xml, netvista.dot11extsetexcludeunencrypted, wlanihv/Dot11ExtSetExcludeUnencrypted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtSetExcludeUnencrypted
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---


# DOT11EXT_SET_EXCLUDE_UNENCRYPTED callback function
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetExcludeUnencrypted</b> function to enable or disable the wireless
  LAN (WLAN) adapter from excluding unencrypted packets it receives while enabled for cipher
  operations.

## Syntax

```
DOT11EXT_SET_EXCLUDE_UNENCRYPTED Dot11extSetExcludeUnencrypted;

DWORD Dot11extSetExcludeUnencrypted(
  HANDLE hDot11SvcHandle,
  BOOL bExcludeUnencrypted
)
{...}
```

## Parameters

`hDot11SvcHandle`

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

`bExcludeUnencrypted`

A Boolean value that, if set to <b>TRUE</b>, configures the WLAN adapter to exclude unencrypted
     packets.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

If the WLAN adapter is enabled to exclude unencrypted packets, the station must exempt received
    packets that match an entry in the station's current EtherType exemption list. The IHV Extensions DLL
    specifies the EtherType exemption list through calls to the 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">
    Dot11ExtSetEtherTypeHandling</a> function.

A call to the 
    <b>Dot11ExtSetExcludeUnencrypted</b> function results in a set request of the 
    <a href="https://msdn.microsoft.com/en-us/library/gg159162.aspx">
    OID_DOT11_EXCLUDE_UNENCRYPTED</a> object identifier (OID) to the Native 802.11 miniport driver that
    manages the WLAN adapter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems.  |
| **Target Platform** | Desktop |
| **Header** | wlanihv.h (include Wlanihv.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/gg159162.aspx">OID_DOT11_EXCLUDE_UNENCRYPTED</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_EXCLUDE_UNENCRYPTED callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>