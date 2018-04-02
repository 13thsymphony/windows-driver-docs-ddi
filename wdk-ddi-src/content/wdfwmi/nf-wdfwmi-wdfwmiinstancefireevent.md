---
UID: NF:wdfwmi.WdfWmiInstanceFireEvent
title: WdfWmiInstanceFireEvent function
author: windows-driver-content
description: The WdfWmiInstanceFireEvent method sends a WMI event to WMI clients that have registered to receive event notification.
old-location: wdf\wdfwmiinstancefireevent.htm
old-project: wdf
ms.assetid: 7bef79ab-78d6-47b6-a3f4-d9733ffcb53d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_1062330c-9a9b-4bd3-a039-e1373c07ceee.xml, WdfWmiInstanceFireEvent, WdfWmiInstanceFireEvent method, kmdf.wdfwmiinstancefireevent, wdf.wdfwmiinstancefireevent, wdfwmi/WdfWmiInstanceFireEvent
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfWmiInstanceFireEvent
product:
- Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---


# WdfWmiInstanceFireEvent function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceFireEvent</b> method sends a WMI event to WMI clients that have registered to receive event notification.

## Syntax

```
NTSTATUS WdfWmiInstanceFireEvent(
  WDFWMIINSTANCE WmiInstance,
  ULONG          EventDataSize,
  PVOID          EventData
);
```

## Parameters

`WmiInstance`

A handle to a WMI instance object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>.

`EventDataSize`

The size, in bytes, of the event data that <i>EventData</i> points to.

`EventData`

A pointer to the event data, or <b>NULL</b> if there is no event data.


## Return Value

<b>WdfWmiInstanceFireEvent</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to communicate with WMI failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The event data buffer was too large.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver should call <b>WdfWmiInstanceFireEvent</b> only if a WMI client has registered for event notification. The driver can determine if it should call <b>WdfWmiInstanceFireEvent</b> by providing an <a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a> callback function or calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551200">WdfWmiProviderIsEnabled</a>.

The driver should place its event-specific data, if any, in the buffer that the <i>EventData</i> parameter points to. The framework adds all of the necessary WMI header information.

For more information about the <b>WdfWmiInstanceFireEvent</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

The following code example sends a WMI event to WMI clients. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MY_WMI_EVENT_DATA eventData;
NTSTATUS  status;

status = WdfWmiInstanceFireEvent(
                                 WmiInstance,
                                 sizeof(eventData),
                                 (PVOID)&amp;eventData
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
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551200">WdfWmiProviderIsEnabled</a>