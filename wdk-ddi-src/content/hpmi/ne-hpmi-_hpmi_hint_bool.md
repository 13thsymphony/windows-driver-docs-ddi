---
UID: NE:hpmi._HPMI_HINT_BOOL
title: _HPMI_HINT_BOOL
author: windows-driver-content
description: Boolean type value used to track availability of HPMI hint data.
old-location: powermeter\hpmi_hint_bool.htm
old-project: powermeter
ms.assetid: E056400C-A0FE-4740-945D-C529C8804DF3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HPMI_HINT_BOOL, *PHPMI_HINT_BOOL, HPMI_HINT_BOOL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: hpmi.h
req.include-header: Hpmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HPMI_HINT_BOOL
req.alt-loc: hpmi.h
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
req.typenames: *PHPMI_HINT_BOOL, HPMI_HINT_BOOL
---

# _HPMI_HINT_BOOL enumeration



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Boolean type value used to track availability of HPMI hint data. 



## -syntax

````
typedef enum _HPMI_HINT_BOOL { 
  HpmiBoolUnavailable  = 0,
  HpmiBoolFalse        = ,
  HpmiBoolTrue         = ,
  HpmiBoolMax          = 
} HPMI_HINT_BOOL;
````


## -enum-fields

### -field HpmiBoolUnavailable

No data is available.


### -field HpmiBoolFalse

Condition is asserted to be false.


### -field HpmiBoolTrue

Condition is asserted to be true.


### -field HpmiBoolMax

Value is not used. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 10, version 1709 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hpmi.h (include Hpmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hpmi\ns-hpmi-_hpmi_battery_utilization_hint.md">HPMI_BATTERY_UTILIZATION_HINT</a>
</dt>
<dt>
<a href="..\hpmi\ni-hpmi-ioctl_hpmi_battery_utilization_hint.md">IOCTL_HPMI_BATTERY_UTILIZATION_HINT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/35934D6C-3FB4-4AD4-AA50-BD3A7790269F">hpmi.h</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20HPMI_HINT_BOOL enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

