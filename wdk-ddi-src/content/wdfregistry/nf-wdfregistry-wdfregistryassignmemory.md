---
UID : NF:wdfregistry.WdfRegistryAssignMemory
title : WdfRegistryAssignMemory function
author : windows-driver-content
description : The WdfRegistryAssignMemory method assigns data that is contained in a specified memory buffer to a specified value name in the registry.
old-location : wdf\wdfregistryassignmemory.htm
old-project : wdf
ms.assetid : 692a9cdf-3cb7-41c1-96a8-28daed13aa60
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdfregistryassignmemory, kmdf.wdfregistryassignmemory, PFN_WDFREGISTRYASSIGNMEMORY, WdfRegistryAssignMemory method, DFRegKeyObjectRef_263749e2-fb1e-4153-9387-32cc256d7fe4.xml, wdfregistry/WdfRegistryAssignMemory, WdfRegistryAssignMemory
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfregistry.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product : Windows 10 or later.
---


# WdfRegistryAssignMemory function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryAssignMemory</b> method assigns data that is contained in a specified memory buffer to a specified value name in the registry.

## Syntax

````
NTSTATUS WdfRegistryAssignMemory(
  _In_     WDFKEY            Key,
  _In_     PCUNICODE_STRING  ValueName,
  _In_     ULONG             ValueType,
  _In_     WDFMEMORY         Memory,
  _In_opt_ PWDFMEMORY_OFFSET MemoryOffsets
);
````

## Parameters

`Key`

A handle to a registry-key object that represents an opened registry key.

`ValueName`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a value name.

`ValueType`

A value that identifies the data type. For a list of data type values, see the <b>Type</b> member of <a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>.

`Memory`

A handle to a framework memory object. This object represents a buffer that contains data that will be assigned to the value name that <i>ValueName</i> points to.

`MemoryOffsets`

A pointer to a driver-supplied <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that identifies a subsection of the buffer that <i>Memory</i> specifies. This parameter is optional and can be <b>NULL</b>.


## Return Value

<b>WdfRegistryAssignMemory</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
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

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignmemory.md">WdfRegistryAssignMemory</a> was not called at IRQL = PASSIVE_LEVEL. 

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The contents of the <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that the <i>MemoryOffsets</i> parameter specified were invalid.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignMemory</b> updates the value's data.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfregistry.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignunicodestring.md">WdfRegistryAssignUnicodeString</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignstring.md">WdfRegistryAssignString</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignulong.md">WdfRegistryAssignULong</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignmultistring.md">WdfRegistryAssignMultiString</a>

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignvalue.md">WdfRegistryAssignValue</a>

<a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>

<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryAssignMemory method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>