---
UID: NF:wdffdo.WdfFdoInitAllocAndQueryProperty
title: WdfFdoInitAllocAndQueryProperty function
author: windows-driver-content
description: The WdfFdoInitAllocAndQueryProperty method allocates a buffer and retrieves a specified device property.
old-location: wdf\wdffdoinitallocandqueryproperty.htm
old-project: wdf
ms.assetid: 9c275d89-e01d-445b-8c60-ae5268cd28c3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdffdo/WdfFdoInitAllocAndQueryProperty, WdfFdoInitAllocAndQueryProperty, WdfFdoInitAllocAndQueryProperty method, PFN_WDFFDOINITALLOCANDQUERYPROPERTY, wdf.wdffdoinitallocandqueryproperty, DFDeviceObjectFdoPdoRef_2de90bea-c2df-4aa7-b64f-b17df042268c.xml, kmdf.wdffdoinitallocandqueryproperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfFdoInitAllocAndQueryProperty
product: Windows
targetos: Windows
req.typenames: "*PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
req.product: Windows 10 or later.
---


# WdfFdoInitAllocAndQueryProperty function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFdoInitAllocAndQueryProperty</b> method allocates a buffer and retrieves a specified device property.

## Syntax

````
NTSTATUS WdfFdoInitAllocAndQueryProperty(
  _In_     PWDFDEVICE_INIT          DeviceInit,
  _In_     DEVICE_REGISTRY_PROPERTY DeviceProperty,
  _In_     POOL_TYPE                PoolType,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES   PropertyMemoryAttributes,
  _Out_    WDFMEMORY                *PropertyMemory
);
````

## Parameters

`DeviceInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

`DeviceProperty`

A <a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>-typed enumerator value that identifies the device property to be retrieved.

`PoolType`

A <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>-typed enumerator value that specifies the type of memory to be allocated.

`PropertyMemoryAttributes`

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that <b>WdfFdoInitAllocAndQueryProperty</b> will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`PropertyMemory`

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object.


## Return Value

If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

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
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure was not obtained from driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

The driver must call <b>WdfFdoInitAllocAndQueryProperty</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

After calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, a driver can obtain device property information by calling <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandqueryproperty.md">WdfDeviceAllocAndQueryProperty</a>.

For more information about the <b>WdfFdoInitAllocAndQueryProperty</b> method, see <a href="https://msdn.microsoft.com/3b988f6d-c50e-412d-85cb-031746535ff4">Creating Device Objects in a Function Driver</a>.

Alternatively, you can use <a href="..\wdffdo\nf-wdffdo-wdffdoinitallocandquerypropertyex.md">WdfFdoInitAllocAndQueryPropertyEx</a> to access device properties that are exposed through the Unified Property Model.


#### Examples

The following code example calls <b>WdfFdoInitAllocAndQueryProperty</b> to obtain a handle to a framework memory object that contains the name of a device's setup class. Then, the example calls <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer that contains the setup class name's Unicode string.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status = STATUS_SUCCESS;
PVOID  pMemoryBuffer = NULL;
WDFMEMORY  memory = NULL;

status = WdfFdoInitAllocAndQueryProperty(
                                         DeviceInit,
                                         DevicePropertyClassName, 
                                         NonPagedPool,
                                         WDF_NO_OBJECT_ATTRIBUTES,
                                         &amp;memory
                                         );
if(NT_SUCCESS(status)){
 pMemoryBuffer = WdfMemoryGetBuffer(
                                    memory,
                                    NULL
                                    );
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
| **Header** | wdffdo.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandqueryproperty.md">WdfDeviceAllocAndQueryProperty</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoinitqueryproperty.md">WdfFdoInitQueryProperty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoInitAllocAndQueryProperty method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>