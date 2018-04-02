---
UID: NF:wdfwmi.WdfWmiProviderIsEnabled
title: WdfWmiProviderIsEnabled function
author: windows-driver-content
description: The WdfWmiProviderIsEnabled method determines if either data collection or event notification is enabled for a specified WMI data provider.
old-location: wdf\wdfwmiproviderisenabled.htm
old-project: wdf
ms.assetid: 7b4fd9ff-09a7-44df-a3e6-0af5d7ea624e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_3231e5bd-aa1c-4bf8-92ef-4b6c29308d95.xml, WdfWmiProviderIsEnabled, WdfWmiProviderIsEnabled method, kmdf.wdfwmiproviderisenabled, wdf.wdfwmiproviderisenabled, wdfwmi/WdfWmiProviderIsEnabled
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfWmiProviderIsEnabled
product:
- Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---


# WdfWmiProviderIsEnabled function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiProviderIsEnabled</b> method determines if either data collection or event notification is enabled for a specified WMI data provider.

## Syntax

```
BOOLEAN WdfWmiProviderIsEnabled(
  WDFWMIPROVIDER           WmiProvider,
  WDF_WMI_PROVIDER_CONTROL ProviderControl
);
```

## Parameters

`WmiProvider`

A handle to a WMI provider object that the driver obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551187">WdfWmiInstanceGetProvider</a>.

`ProviderControl`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553078">WDF_WMI_PROVIDER_CONTROL</a>-typed value that specifies one of the types of control functions (data collection or event notification) that a WMI data provider can support.


## Return Value

<b>WdfWmiProviderIsEnabled</b> returns <b>TRUE</b> if the capability that the <i>ProviderControl</i> parameter specifies is enabled and <b>FALSE</b> otherwise.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A driver that does not provide an <a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a> callback function can call <b>WdfWmiProviderIsEnabled</b> to determine if data collection or event notification is enabled.


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

<a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553078">WDF_WMI_PROVIDER_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551187">WdfWmiInstanceGetProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>