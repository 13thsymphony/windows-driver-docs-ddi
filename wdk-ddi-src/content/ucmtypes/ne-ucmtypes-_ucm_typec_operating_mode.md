---
UID: NE.ucmtypes._UCM_TYPEC_OPERATING_MODE
title: _UCM_TYPEC_OPERATING_MODE
author: windows-driver-content
description: Defines operating modes of a USB Type-C connector.
old-location: buses\ucm_type_c_operating_mode.htm
old-project: usbref
ms.assetid: B64849A6-DDB1-4BD1-B4B6-1E38DE9237E5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCM_TYPEC_OPERATING_MODE, UCM_TYPEC_OPERATING_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_TYPEC_OPERATING_MODE
req.alt-loc: Ucmtypes.h
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

# _UCM_TYPEC_OPERATING_MODE enumeration



## -description
Defines operating modes of a USB Type-C connector.



## -syntax

````
typedef enum _UCM_TYPEC_OPERATING_MODE { 
  UcmTypeCOperatingModeInvalid  = 0x0,
  UcmTypeCOperatingModeDfp      = 0x1,
  UcmTypeCOperatingModeUfp      = 0x2,
  UcmTypeCOperatingModeDrp      = 0x4
} UCM_TYPEC_OPERATING_MODE;
````


## -enum-fields

### -field UcmTypeCOperatingModeInvalid

Indicates the operating mode is invalid.


### -field UcmTypeCOperatingModeDfp

Indicates the operating mode is set to downstream-facing port.


### -field UcmTypeCOperatingModeUfp

Indicates the operating mode is set to upstream-facing port.


### -field UcmTypeCOperatingModeDrp

Indicates the operating mode is set to dual-role port. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucmtypes.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.ucm_connector_type_c_config_init">UCM_CONNECTOR_TYPEC_CONFIG_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_TYPEC_OPERATING_MODE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

