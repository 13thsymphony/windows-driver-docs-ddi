---
UID: NS:charging._CONFIGURABLE_CHARGER_PROPERTY_HEADER
title: "_CONFIGURABLE_CHARGER_PROPERTY_HEADER"
author: windows-driver-content
description: The CONFIGURABLE_CHARGER_PROPERTY_HEADER structure is a header that is used to create your own structure as an input to IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY.
old-location: battery\configurable_charger_property_header.htm
old-project: battery
ms.assetid: 1A188828-51CE-4C80-92CB-2C01861082CD
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCONFIGURABLE_CHARGER_PROPERTY_HEADER, CONFIGURABLE_CHARGER_PROPERTY_HEADER, CONFIGURABLE_CHARGER_PROPERTY_HEADER structure [Battery Devices], PCONFIGURABLE_CHARGER_PROPERTY_HEADER, PCONFIGURABLE_CHARGER_PROPERTY_HEADER structure pointer [Battery Devices], _CONFIGURABLE_CHARGER_PROPERTY_HEADER, battery.configurable_charger_property_header, charging/CONFIGURABLE_CHARGER_PROPERTY_HEADER, charging/PCONFIGURABLE_CHARGER_PROPERTY_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: charging.h
req.include-header: Charging.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	charging.h
api_name:
-	CONFIGURABLE_CHARGER_PROPERTY_HEADER
product:
- Windows
targetos: Windows
req.typenames: CONFIGURABLE_CHARGER_PROPERTY_HEADER, *PCONFIGURABLE_CHARGER_PROPERTY_HEADER
---

# _CONFIGURABLE_CHARGER_PROPERTY_HEADER structure
The CONFIGURABLE_CHARGER_PROPERTY_HEADER structure is a header that is used to create your own structure as an input to <a href="https://msdn.microsoft.com/library/windows/hardware/mt186650">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>.

## Syntax
```
typedef struct _CONFIGURABLE_CHARGER_PROPERTY_HEADER {
  ULONG Size;
  GUID  ChargerId;
  ULONG PropertyId;
} CONFIGURABLE_CHARGER_PROPERTY_HEADER, *PCONFIGURABLE_CHARGER_PROPERTY_HEADER;
```

## Members


`Size`

Size of the structure.

`ChargerId`

The charger ID.

`PropertyId`

The ID of the property to be configured.

## Remarks
Extend this structure to add your own values for the input to <a href="https://msdn.microsoft.com/library/windows/hardware/mt186650">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>. Create a new structure with <b>CONFIGURABLE_CHARGER_PROPERTY_HEADER</b> as the first field, and one or more values after it that correspond to your <b>PropertyId</b>. Here are two example structures.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct SET_MY_CHARGER_VOLTAGE {
    CONFIGURABLE_CHARGER_PROPERTY_HEADER Header;
    ULONG Voltage;
};</pre>
</td>
</tr>
</table></span></div>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct SET_MY_CHARGER_CURRENT_AND_VOLTAGE {
    CONFIGURABLE_CHARGER_PROPERTY_HEADER Header;
    ULONG Current;
    ULONG Voltage;
};</pre>
</td>
</tr>
</table></span></div>
Make sure you set <b>Header.Size</b> to the appropriate size of your new structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Header.Size = sizeof(SET_MY_CHARGER_VOLTAGE);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | charging.h (include Charging.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186650">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>