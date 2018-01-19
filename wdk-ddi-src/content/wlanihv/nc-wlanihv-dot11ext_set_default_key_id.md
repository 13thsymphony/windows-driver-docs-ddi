---
UID : NC:wlanihv.DOT11EXT_SET_DEFAULT_KEY_ID
title : DOT11EXT_SET_DEFAULT_KEY_ID
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11extsetdefaultkeyid.htm
old-project : netvista
ms.assetid : 405da147-9b41-4563-8694-6619f86ed366
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wlanihv.h
req.include-header : Wlanihv.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : Dot11ExtSetDefaultKeyId
req.alt-loc : wlanihv.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W"
req.product : Windows 10 or later.
---


# DOT11EXT_SET_DEFAULT_KEY_ID callback function


## Syntax

```
DOT11EXT_SET_DEFAULT_KEY_ID Dot11extSetDefaultKeyId;

DWORD Dot11extSetDefaultKeyId(
  HANDLE hDot11SvcHandle,
  ULONG uDefaultKeyId
)
{...}
```

## Parameters

`hDot11SvcHandle`

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

`uDefaultKeyId`

The index value of the key within the adapter's default or per-station cipher key tables.
     

For standard 802.11 cipher algorithms, such as WEP or TKIP, 
     <i>uDefaultKeyId</i> must be from 0 through 3. For a proprietary cipher algorithm developed by an IHV, 
     <i>uDefaultKeyId</i> can be any value within the range defined by the IHV.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

The default key identifier (ID) specifies the index of a cipher key in the adapter's default key and
    per-station default key tables that the adapter uses for data encryption. The adapter uses the cipher key
    referenced by the default key ID as the default encryption key for transmitted packets unless a
    key-mapping key exists for the destination media access control (MAC) address. For more information about
    these cipher key types, see 
    <a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>.

A call to the 
    <b>Dot11ExtSetDefaultKeyId</b> function results in a set request of the 
    <a href="netvista.oid_dot11_cipher_default_key_id">
    OID_DOT11_CIPHER_DEFAULT_KEY_ID</a> object identifier (OID) to the Native 802.11 miniport driver, which
    manages the WLAN adapter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wlanihv.h (include Wlanihv.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569120">OID_DOT11_CIPHER_DEFAULT_KEY_ID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_DEFAULT_KEY_ID callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>