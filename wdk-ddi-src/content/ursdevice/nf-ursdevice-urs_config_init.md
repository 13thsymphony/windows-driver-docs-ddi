---
UID: NF.ursdevice.URS_CONFIG_INIT
title: URS_CONFIG_INIT function
author: windows-driver-content
description: Initializes a URS_CONFIG structure.
old-location: buses\urs_config_init.htm
old-project: usbref
ms.assetid: 72229643-1177-4884-94A9-89920A5488A6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: URS_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: URS_CONFIG_INIT
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

# URS_CONFIG_INIT function



## -description
Initializes a <a href="buses.urs_config">URS_CONFIG</a> structure. 



## -syntax

````
FORCEINLINE void URS_CONFIG_INIT(
  _Out_ PURS_CONFIG                                 Config,
  _In_  URS_HOST_INTERFACE_TYPE                     HostInterfaceType,
  _In_  PFN_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtUrsFilterRemoveResourceRequirements
);
````


## -parameters

### -param Config [out]

 A pointer to a <a href="buses.urs_config">URS_CONFIG</a> structure to initialize.


### -param HostInterfaceType [in]

 A <a href="buses.urs_host_interface_type">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of host controller that the dual-role controller implements.


### -param EvtUrsFilterRemoveResourceRequirements [in]

 A  pointer to a <a href="buses.evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function that is implemented by the  client driver.


## -returns
This function does not return a value.


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
<a href="buses.urs_config">URS_CONFIG</a>
</dt>
<dt>
<a href="buses.ursdeviceinitialize">UrsDeviceInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20URS_CONFIG_INIT function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

