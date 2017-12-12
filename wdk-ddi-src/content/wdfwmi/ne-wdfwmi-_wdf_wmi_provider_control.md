---
UID: NE.wdfwmi._WDF_WMI_PROVIDER_CONTROL
title: _WDF_WMI_PROVIDER_CONTROL
author: windows-driver-content
description: The WDF_WMI_PROVIDER_CONTROL enumeration defines the type of control functions that a WMI data provider can support.
old-location: wdf\wdf_wmi_provider_control.htm
old-project: wdf
ms.assetid: c545b0a6-bb36-47a7-b55c-ee7eed5ade3a
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_WMI_PROVIDER_CONTROL, WDF_WMI_PROVIDER_CONTROL
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
req.alt-api: WDF_WMI_PROVIDER_CONTROL
req.alt-loc: wdfwmi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# _WDF_WMI_PROVIDER_CONTROL enumeration



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_PROVIDER_CONTROL</b> enumeration defines the type of control functions that a WMI data provider can support.



## -syntax

````
typedef enum _WDF_WMI_PROVIDER_CONTROL { 
  WdfWmiControlInvalid   = 0,
  WdfWmiEventControl     = 1,
  WdfWmiInstanceControl  = 2
} WDF_WMI_PROVIDER_CONTROL;
````


## -enum-fields

### -field WdfWmiControlInvalid

For internal use only.


### -field WdfWmiEventControl

The driver must enable or disable delivering events for a provider instance.


### -field WdfWmiInstanceControl

The driver must enable or disable collecting data for a provider instance.


## -remarks
The <b>WDF_WMI_PROVIDER_CONTROL</b> enumeration is used as an input parameter to the <a href="wdf.wdfwmiproviderisenabled">WdfWmiProviderIsEnabled</a> method and the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a> callback function.


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
<a href="wdf.wdfwmiproviderisenabled">WdfWmiProviderIsEnabled</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WMI_PROVIDER_CONTROL enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

