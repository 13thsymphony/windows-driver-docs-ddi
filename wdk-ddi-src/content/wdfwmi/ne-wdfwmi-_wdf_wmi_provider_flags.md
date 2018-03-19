---
UID: NE:wdfwmi._WDF_WMI_PROVIDER_FLAGS
title: "_WDF_WMI_PROVIDER_FLAGS"
author: windows-driver-content
description: The WDF_WMI_PROVIDER_FLAGS enumeration defines configuration flags for a driver's WMI data provider.
old-location: wdf\wdf_wmi_provider_flags.htm
old-project: wdf
ms.assetid: 85b1a4b4-53e0-4663-b813-18801f8b639b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_e093a379-bdc9-4b69-90e8-294b9d55eeea.xml, WDF_WMI_PROVIDER_FLAGS, WDF_WMI_PROVIDER_FLAGS enumeration, WdfWmiProviderEventOnly, WdfWmiProviderExpensive, WdfWmiProviderTracing, WdfWmiProviderValidFlags, _WDF_WMI_PROVIDER_FLAGS, kmdf.wdf_wmi_provider_flags, wdf.wdf_wmi_provider_flags, wdfwmi/WDF_WMI_PROVIDER_FLAGS, wdfwmi/WdfWmiProviderEventOnly, wdfwmi/WdfWmiProviderExpensive, wdfwmi/WdfWmiProviderTracing, wdfwmi/WdfWmiProviderValidFlags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfwmi.h
api_name:
-	WDF_WMI_PROVIDER_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# _WDF_WMI_PROVIDER_FLAGS Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_PROVIDER_FLAGS</b> enumeration defines configuration flags for a driver's WMI data provider.

## Syntax
````
typedef enum _WDF_WMI_PROVIDER_FLAGS { 
  WdfWmiProviderEventOnly   = 0x0001,
  WdfWmiProviderExpensive   = 0x0002,
  WdfWmiProviderTracing     = 0x0004,
  WdfWmiProviderValidFlags  = WdfWmiProviderEventOnly | WdfWmiProviderExpensive | WdfWmiProviderTracing
} WDF_WMI_PROVIDER_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>WdfWmiProviderEventOnly</td>
                    <td>WMI clients can receive notification of WMI events, but they cannot query or set instance data. The driver can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancefireevent.md">WdfWmiInstanceFireEvent</a>, but it does not provide any instance-specific callback functions.</td>
                </tr>
            
                <tr>
                    <td>WdfWmiProviderExpensive</td>
                    <td>Collecting the provider's data can potentially affect the driver's performance, so the driver will not collect data unless a WMI client has registered to use it. The framework calls the driver's <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a> callback function, passing the <b>WdfWmiInstanceControl</b> value (from the <a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a> enumeration), to inform the driver to begin collecting data. If the driver does not provide an <i>EvtWmiProviderFunctionControl</i> callback function, it can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>.</td>
                </tr>
            
                <tr>
                    <td>WdfWmiProviderTracing</td>
                    <td>The WMI data provider supports WMI event tracing. The driver can obtain the tracing handle by calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidergettracinghandle.md">WdfWmiProviderGetTracingHandle</a>. If this flag is set, no other flags can be set.</td>
                </tr>
            
                <tr>
                    <td>WdfWmiProviderValidFlags</td>
                    <td>The bitwise OR of all flags. Drivers should not use this value.</td>
                </tr>
</table>

## Remarks

The <b>WDF_WMI_PROVIDER_FLAGS</b> enumeration is used in the <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfwmi.h (include Wdf.h) |

## See Also

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidergettracinghandle.md">WdfWmiProviderGetTracingHandle</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancefireevent.md">WdfWmiInstanceFireEvent</a>



<a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WdfWmiInstanceControl</a>



<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>