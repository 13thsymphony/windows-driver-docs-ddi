---
UID: NC:wlanihv.DOT11EXTIHV_DEINIT_ADAPTER
title: DOT11EXTIHV_DEINIT_ADAPTER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvdeinitadapter.htm
old-project: netvista
ms.assetid: bf2e7ed3-cefc-47f3-a21b-aea3f0e569fe
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _DRIVER_INFO_8W, DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W, DRIVER_INFO_8
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
req.alt-api: Dot11ExtIhvDeinitAdapter
req.alt-loc: wlanihv.h
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
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_DEINIT_ADAPTER callback



## -description

## -prototype

````
DOT11EXTIHV_DEINIT_ADAPTER Dot11ExtIhvDeinitAdapter;

VOID APIENTRY Dot11ExtIhvDeinitAdapter(
  _In_opt_ HANDLE hIhvExtAdapter
)
{ ... }
````


## -parameters

### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


## -returns
None


## -remarks
The operating system calls the 
    <i>Dot11ExtIhvDeinitAdapter</i> function whenever a WLAN adapter becomes unavailable and is disabled for
    use, such as when a PCMCIA adapter is removed.

The operating system also calls the 
    <i>Dot11ExtIhvDeinitAdapter</i> function for every adapter managed by the IHV Extensions DLL before the
    operating system unloads the DLL. In this situation, the operating system calls the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_service.md">Dot11ExtIhvDeinitService</a> IHV
    Handler function after the last WLAN adapter has been halted through a call to the 
    <i>Dot11ExtIhvDeinitAdapter</i> function.

For more information about operations that are performed when the WLAN adapter is removed, see 
    <a href="https://msdn.microsoft.com/2181d284-7987-48db-b7a4-d1296d8313ed">802.11 WLAN Adapter Removal</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wlanihv.h (include Wlanihv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_service.md">Dot11ExtIhvDeinitService</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_extensibility_functions">Native 802.11 IHV
   Extensibility Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_DEINIT_ADAPTER callback function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

