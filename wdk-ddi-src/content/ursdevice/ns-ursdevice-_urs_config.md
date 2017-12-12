---
UID: NS.URSDEVICE._URS_CONFIG
title: _URS_CONFIG
author: windows-driver-content
description: Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling URS_CONFIG_INIT.
old-location: buses\urs_config.htm
old-project: usbref
ms.assetid: 3857CA53-6992-410A-96D1-EEA9CC586EDF
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _URS_CONFIG, URS_CONFIG, *PURS_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: URS_CONFIG
req.alt-loc: Ursdevice.h
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

# _URS_CONFIG structure



## -description
Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling <a href="buses.urs_config_init">URS_CONFIG_INIT</a>.



## -syntax

````
typedef struct _URS_CONFIG {
  ULONG                                       Size;
  URS_HOST_INTERFACE_TYPE                     HostInterfaceType;
  PFN_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtUrsFilterRemoveResourceRequirements;
  PFN_URS_SET_ROLE                            EvtUrsSetRole;
} URS_CONFIG, *PURS_CONFIG;
````


## -struct-fields

### -field Size

The size of this structure.


### -field HostInterfaceType

A <a href="buses.urs_host_interface_type">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of USB host controller: EHCI, xHCI, or other.


### -field EvtUrsFilterRemoveResourceRequirements

A pointer to an <a href="buses.evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function.


### -field EvtUrsSetRole

A pointer to an <a href="..\ursdevice\nc-ursdevice-evt_urs_set_role.md">EVT_URS_SET_ROLE</a> callback function.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ursdevice.h (include Urscx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.ursdeviceinitialize">UrsDeviceInitialize</a>
</dt>
<dt>
<a href="buses.urs_config_init">URS_CONFIG_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20URS_CONFIG structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

