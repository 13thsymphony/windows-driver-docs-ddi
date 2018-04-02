---
UID: NF:wdfwmi.WdfWmiInstanceDeregister
title: WdfWmiInstanceDeregister function
author: windows-driver-content
description: The WdfWmiInstanceDeregister method deregisters a specified instance of a WMI data provider from the system's WMI service.
old-location: wdf\wdfwmiinstancederegister.htm
old-project: wdf
ms.assetid: 2167504e-ca92-4427-9101-04a2c2bf66df
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_4e04e7da-3a14-4bd4-a430-8f5f3624b61a.xml, WdfWmiInstanceDeregister, WdfWmiInstanceDeregister method, kmdf.wdfwmiinstancederegister, wdf.wdfwmiinstancederegister, wdfwmi/WdfWmiInstanceDeregister
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
-	WdfWmiInstanceDeregister
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---


# WdfWmiInstanceDeregister function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceDeregister</b> method deregisters a specified instance of a WMI data provider from the system's WMI service.

## Syntax

```
void WdfWmiInstanceDeregister(
  WDFWMIINSTANCE WmiInstance
);
```

## Parameters

`WmiInstance`

A handle to a WMI instance object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about the <b>WdfWmiInstanceDeregister</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/initializing-wmi-support-in-your-driver">Registering Provider Instances</a>. For more information about WMI, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff551190">WdfWmiInstanceRegister</a> deregisters the provider instance synchronously (that is, before returning) if it is called at IRQL = PASSIVE_LEVEL and asynchronously if it is called at IRQL &gt; PASSIVE_LEVEL. 


#### Examples

The following code example deregisters a specified instance of a WMI data provider from the system's WMI service.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfWmiInstanceDeregister(wmiInstance);</pre>
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551190">WdfWmiInstanceRegister</a>