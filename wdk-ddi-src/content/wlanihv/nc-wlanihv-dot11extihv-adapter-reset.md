---
UID: NC.wlanihv.DOT11EXTIHV_ADAPTER_RESET
title: DOT11EXTIHV_ADAPTER_RESET
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvadapterreset.htm
old-project: netvista
ms.assetid: c1e8cce7-6fa4-45d3-a8c8-9f2ef0a8e846
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PrintPropertyValue, PrintPropertyValue
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
req.alt-api: Dot11ExtIhvAdapterReset
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
req.iface: 
req.product: Windows 10 or later.
---

# DOT11EXTIHV_ADAPTER_RESET callback



## -description

## -prototype

````
DOT11EXTIHV_ADAPTER_RESET Dot11ExtIhvAdapterReset;

DWORD APIENTRY Dot11ExtIhvAdapterReset(
  _In_opt_ HANDLE hIhvExtAdapter
)
{ ... }
````


## -parameters
<dl>

### -param hIhvExtAdapter [in, optional]

<dd>
<p>The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.</p>
</dd>
</dl>

## -returns
<p>If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.</p>

## -remarks
<p>The operating system calls 
    <i>Dot11ExtIhvAdapterReset</i> whenever one of the following events occurs.</p>

<p>The WLAN adapter performs a disconnection operation. For more information about this operation, see 
      <a href="netvista.disconnection_operations">Disconnection Operations</a>.</p>

<p>The operating system resets the Native 802.11 miniport driver, which manages the adapter, through a
      set request of 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>.</p>

<p>The 
    <i>Dot11ExtIhvAdapterReset</i> function must restore the WLAN adapter to the same state as when the DLL's 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a> function
    was called.</p>

<p>For more information about the reset operation for WLAN adapters, see 
    <a href="netvista.802_11_wlan_adapter_reset">802.11 WLAN Adapter Reset</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_ADAPTER_RESET callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
