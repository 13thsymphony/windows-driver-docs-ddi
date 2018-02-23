---
UID: NF:wdfwmi.WdfWmiProviderIsEnabled
title: WdfWmiProviderIsEnabled function
author: windows-driver-content
description: The WdfWmiProviderIsEnabled method determines if either data collection or event notification is enabled for a specified WMI data provider.
old-location: wdf\wdfwmiproviderisenabled.htm
old-project: wdf
ms.assetid: 7b4fd9ff-09a7-44df-a3e6-0af5d7ea624e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfWmiProviderIsEnabled, DFWMIRef_3231e5bd-aa1c-4bf8-92ef-4b6c29308d95.xml, wdf.wdfwmiproviderisenabled, kmdf.wdfwmiproviderisenabled, wdfwmi/WdfWmiProviderIsEnabled, WdfWmiProviderIsEnabled method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfWmiProviderIsEnabled
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---


# WdfWmiProviderIsEnabled function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiProviderIsEnabled</b> method determines if either data collection or event notification is enabled for a specified WMI data provider.

## Syntax

````
BOOLEAN WdfWmiProviderIsEnabled(
  _In_ WDFWMIPROVIDER           WmiProvider,
  _In_ WDF_WMI_PROVIDER_CONTROL ProviderControl
);
````

## Parameters

`WmiProvider`

A handle to a WMI provider object that the driver obtained by calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> or <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a>.

`ProviderControl`

A <a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a>-typed value that specifies one of the types of control functions (data collection or event notification) that a WMI data provider can support.


## Return Value

<b>WdfWmiProviderIsEnabled</b> returns <b>TRUE</b> if the capability that the <i>ProviderControl</i> parameter specifies is enabled and <b>FALSE</b> otherwise.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A driver that does not provide an <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a> callback function can call <b>WdfWmiProviderIsEnabled</b> to determine if data collection or event notification is enabled.


#### Examples

The following code example determines if event notification is enabled for a specified WMI data provider.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN eventNotifEnabled;

eventNotifEnabled = WdfWmiProviderIsEnabled(
                                            wmiProvider,
                                            WdfWmiEventControl
                                            );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfwmi.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>



<a href="..\wdfwmi\ne-wdfwmi-_wdf_wmi_provider_control.md">WDF_WMI_PROVIDER_CONTROL</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiProviderIsEnabled method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>