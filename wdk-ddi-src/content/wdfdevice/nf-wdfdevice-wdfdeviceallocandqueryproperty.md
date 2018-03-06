---
UID: NF:wdfdevice.WdfDeviceAllocAndQueryProperty
title: WdfDeviceAllocAndQueryProperty function
author: windows-driver-content
description: The WdfDeviceAllocAndQueryProperty method allocates a buffer and retrieves a specified device property.
old-location: wdf\wdfdeviceallocandqueryproperty.htm
old-project: wdf
ms.assetid: f921fee7-e2c0-4e0f-a78b-d2dff8af97a2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d093b9da-de6b-467d-a6bd-c25d7a4145f8.xml, WdfDeviceAllocAndQueryProperty, WdfDeviceAllocAndQueryProperty method, kmdf.wdfdeviceallocandqueryproperty, wdf.wdfdeviceallocandqueryproperty, wdfdevice/WdfDeviceAllocAndQueryProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
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
-	WdfDeviceAllocAndQueryProperty
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceAllocAndQueryProperty function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceAllocAndQueryProperty</b> method allocates a buffer and retrieves a specified device property.

## Syntax

````
NTSTATUS WdfDeviceAllocAndQueryProperty(
  _In_     WDFDEVICE                Device,
  _In_     DEVICE_REGISTRY_PROPERTY DeviceProperty,
  _In_     POOL_TYPE                PoolType,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES   PropertyMemoryAttributes,
  _Out_    WDFMEMORY                *PropertyMemory
);
````

## Parameters

`Device`

A handle to a framework device object.

`DeviceProperty`

A <a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>-typed enumerator that identifies the device property to be retrieved.

`PoolType`

A <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>-typed enumerator that specifies the type of memory to be allocated.

`PropertyMemoryAttributes`

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`PropertyMemory`

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object.


## Return Value

If the operation succeeds, <b>WdfDeviceAllocAndQueryProperty</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER or STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>DeviceProperty</i> value is invalid.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The device's drivers have not yet reported the device's properties.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfDeviceAllocAndQueryProperty</b> method determines the amount of memory that is necessary to hold the requested device property. It allocates enough memory to hold the data, and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>. 

Alternatively, you can use <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandquerypropertyex.md">WdfDeviceAllocAndQueryPropertyEx</a> to access device properties that are exposed through the Unified Property Model.


#### Examples

The following code example initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure with attributes for the framework memory object that the framework will create for the requested property. Then, the example calls <b>WdfDeviceAllocAndQueryProperty</b> to obtain the <b>DevicePropertyPhysicalDeviceObjectName</b> property. After <b>WdfDeviceAllocAndQueryProperty</b> returns, the driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer that contains the name string.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  attributes;
NTSTATUS  status;
WDFDEVICE  device;
WDFMEMORY  memory;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = device;

status = WdfDeviceAllocAndQueryProperty(device,
                                        DevicePropertyPhysicalDeviceObjectName,
                                        NonPagedPool,
                                        &amp;attributes,
                                        &amp;memory
                                        );
if (!NT_SUCCESS(status)) {
    return STATUS_UNSUCCESSFUL;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryproperty.md">WdfDeviceQueryProperty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAllocAndQueryProperty method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>