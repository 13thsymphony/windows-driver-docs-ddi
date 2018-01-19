---
UID : NC:wlanihv.DOT11EXTIHV_RECEIVE_INDICATION
title : DOT11EXTIHV_RECEIVE_INDICATION
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11extihvreceiveindication.htm
old-project : netvista
ms.assetid : b4d5c33e-563d-459c-90da-a2912c82d1cd
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
req.alt-api : Dot11ExtIhvReceiveIndication
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


# DOT11EXTIHV_RECEIVE_INDICATION callback function


## Syntax

```
DOT11EXTIHV_RECEIVE_INDICATION Dot11extihvReceiveIndication;

DWORD Dot11extihvReceiveIndication(
  HANDLE hIhvExtAdapter,
  DOT11EXT_IHV_INDICATION_TYPE indicationType,
  ULONG uBufferLength,
  LPVOID pvBuffer
)
{...}
```

## Parameters

`hIhvExtAdapter`

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

`indicationType`

The 
     <a href="..\wlanihv\ne-wlanihv-_dot11ext_ihv_indication_type.md">
     DOT11EXT_IHV_INDICATION_TYPE</a> indication type.

`uBufferLength`

The length, in bytes, of the data within the buffer that is referenced by the 
     <i>pvBuffer</i> parameter.

`pvBuffer`

The pointer to a buffer, allocated by the operating system, which contains the notification data.
     The IHV is responsible for defining the format of the notification data.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

When the Native 802.11 miniport driver, which manages the WLAN adapter, makes an 
    <a href="netvista.ndis_status_media_specific_indication">
    NDIS_STATUS_MEDIA_SPECIFIC_INDICATION</a> indication, the operating system forwards the notification
    data to the IHV Extensions DLL by calling the 
    <i>Dot11ExtIhvReceiveIndication</i> function.

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
<a href="..\wlanihv\ne-wlanihv-_dot11ext_ihv_indication_type.md">DOT11EXT_IHV_INDICATION_TYPE</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="netvista.ndis_status_media_specific_indication">
   NDIS_STATUS_MEDIA_SPECIFIC_INDICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_RECEIVE_INDICATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>