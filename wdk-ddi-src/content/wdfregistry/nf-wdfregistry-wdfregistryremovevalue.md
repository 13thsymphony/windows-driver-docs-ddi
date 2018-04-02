---
UID: NF:wdfregistry.WdfRegistryRemoveValue
title: WdfRegistryRemoveValue function
author: windows-driver-content
description: The WdfRegistryRemoveValue method removes a specified value and its data from a specified registry key.
old-location: wdf\wdfregistryremovevalue.htm
old-project: wdf
ms.assetid: 485583b2-2736-4ecf-b58c-65b4d4f47a20
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_2928cd6b-7fb0-46aa-bcc4-4def625bb2fe.xml, WdfRegistryRemoveValue, WdfRegistryRemoveValue method, kmdf.wdfregistryremovevalue, wdf.wdfregistryremovevalue, wdfregistry/WdfRegistryRemoveValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRegistryRemoveValue
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---


# WdfRegistryRemoveValue function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryRemoveValue</b> method removes a specified value and its data from a specified registry key.

## Syntax

```
NTSTATUS WdfRegistryRemoveValue(
  WDFKEY           Key,
  PCUNICODE_STRING ValueName
);
```

## Parameters

`Key`

A handle to a registry-key object that represents an opened registry key.

`ValueName`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a value name.


## Return Value

<b>WdfRegistryRemoveValue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549932">WdfRegistryRemoveValue</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with KEY_SET_VALUE access.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example removes the <b>MyValue</b> value and its data from a specified registry key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DECLARE_CONST_UNICODE_STRING(valueName, L"MyValue");

status = WdfRegistryRemoveValue(
                                Key,
                                &amp;valueName
                                );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfregistry.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>