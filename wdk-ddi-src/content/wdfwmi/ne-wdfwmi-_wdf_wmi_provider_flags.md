---
UID: NE:wdfwmi._WDF_WMI_PROVIDER_FLAGS
title: _WDF_WMI_PROVIDER_FLAGS
author: windows-driver-content
description: The WDF_WMI_PROVIDER_FLAGS enumeration defines configuration flags for a driver's WMI data provider.
old-location: wdf\wdf_wmi_provider_flags.htm
old-project: wdf
ms.assetid: 85b1a4b4-53e0-4663-b813-18801f8b639b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _WDF_WMI_PROVIDER_FLAGS, WDF_WMI_PROVIDER_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_WMI_PROVIDER_FLAGS
req.alt-loc: wdfwmi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# _WDF_WMI_PROVIDER_FLAGS enumeration



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_PROVIDER_FLAGS</b> enumeration defines configuration flags for a driver's WMI data provider.



## -syntax

````
typedef enum _WDF_WMI_PROVIDER_FLAGS { 
  WdfWmiProviderEventOnly   = 0x0001,
  WdfWmiProviderExpensive   = 0x0002,
  WdfWmiProviderTracing     = 0x0004,
  WdfWmiProviderValidFlags  = WdfWmiProviderEventOnly | WdfWmiProviderExpensive | WdfWmiProviderTracing
} WDF_WMI_PROVIDER_FLAGS;
````


## -enum-fields

### -field WdfWmiProviderEventOnly

WMI clients can receive notification of WMI events, but they cannot query or set instance data. The driver can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancefireevent.md">WdfWmiInstanceFireEvent</a>, but it does not provide any instance-specific callback functions.


### -field WdfWmiProviderExpensive

Collecting the provider's data can potentially affect the driver's performance, so the driver will not collect data unless a WMI client has registered to use it. The framework calls the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a> callback function, passing the <b>WdfWmiInstanceControl</b> value (from the <a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a> enumeration), to inform the driver to begin collecting data. If the driver does not provide an <i>EvtWmiProviderFunctionControl</i> callback function, it can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>.


### -field WdfWmiProviderTracing

The WMI data provider supports WMI event tracing. The driver can obtain the tracing handle by calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidergettracinghandle.md">WdfWmiProviderGetTracingHandle</a>. If this flag is set, no other flags can be set.


### -field WdfWmiProviderValidFlags

The bitwise OR of all flags. Drivers should not use this value.


## -remarks
The <b>WDF_WMI_PROVIDER_FLAGS</b> enumeration is used in the <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure.


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
<dt>Wdfwmi.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>
</dt>
<dt>
<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WdfWmiInstanceControl</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancefireevent.md">WdfWmiInstanceFireEvent</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidergettracinghandle.md">WdfWmiProviderGetTracingHandle</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WMI_PROVIDER_FLAGS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

