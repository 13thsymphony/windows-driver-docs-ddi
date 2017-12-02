---
UID: NE.windot11._DOT11_TEMP_TYPE
title: DOT11_TEMP_TYPE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_temp_type.htm
old-project: netvista
ms.assetid: 73275e2e-b738-4adc-b89e-2cd152de6c75
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PRINTER_EVENT_ATTRIBUTES_INFO, PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_TEMP_TYPE
req.alt-loc: windot11.h
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

# DOT11_TEMP_TYPE enumeration



## -description

## -syntax

````
typedef enum _DOT11_TEMP_TYPE { 
  dot11_temp_type_unknown  = 0,
  dot11_temp_type_1        = 1,
  dot11_temp_type_2        = 2
} DOT11_TEMP_TYPE, *PDOT11_TEMP_TYPE;
````


## -enum-fields
<dl>

### -field dot11_temp_type_unknown

<dd>
<p>An uninitialized or unknown temperature type.</p>
</dd>

### -field dot11_temp_type_1

<dd>
<p>The commercial temperature range from 0 through 40 degrees Celsius.</p>
</dd>

### -field dot11_temp_type_2

<dd>
<p>The industrial temperature range from -30 through 70 degrees Celsius.</p>
</dd>
</dl>

## -remarks
<p>There are different operating temperature requirements dependent on the anticipated environmental
    conditions. The DOT11_TEMP_TYPE enumeration describes a PHY's operating temperature range capability.</p>

## -requirements
<table>
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
<dt>Windot11.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-dot11-phy-attributes.md">DOT11_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569431">OID_DOT11_TEMP_TYPE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_TEMP_TYPE enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
