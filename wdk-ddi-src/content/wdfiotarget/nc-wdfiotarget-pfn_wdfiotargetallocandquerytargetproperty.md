---
UID: NC:wdfiotarget.PFN_WDFIOTARGETALLOCANDQUERYTARGETPROPERTY
title: PFN_WDFIOTARGETALLOCANDQUERYTARGETPROPERTY function
author: windows-driver-content
description: The WdfIoTargetAllocAndQueryTargetProperty method allocates a buffer and retrieves a specified device property for a specified I/O target.
old-location: wdf\wdfiotargetallocandquerytargetproperty.htm
old-project: wdf
ms.assetid: 9b66ba25-7723-4805-aa7c-7091a18d749b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFIOTARGETALLOCANDQUERYTARGETPROPERTY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfIoTargetAllocAndQueryTargetProperty
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY
req.product: Windows 10 or later.
---

# PFN_WDFIOTARGETALLOCANDQUERYTARGETPROPERTY function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetAllocAndQueryTargetProperty</b> method allocates a buffer and retrieves a specified device property for a specified I/O target.



## -syntax

````
NTSTATUS WdfIoTargetAllocAndQueryTargetProperty(
  _In_     WDFIOTARGET              IoTarget,
  _In_     DEVICE_REGISTRY_PROPERTY DeviceProperty,
  _In_     POOL_TYPE                PoolType,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES   PropertyMemoryAttributes,
  _Out_    WDFMEMORY                *PropertyMemory
);
````


## -parameters

### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.


### -param DeviceProperty [in]

A <a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>-typed value that identifies the device property to be retrieved.


### -param PoolType [in]

A <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated.


### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PropertyMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object. 


## -returns
<b>WdfIoTargetAllocAndQueryTargetProperty</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER or STATUS_INVALID_PARAMETER_2</b></dt>
</dl>The value that the <i>DeviceProperty</i> parameter specified was invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The device's drivers have not yet reported the device's properties.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The <b>WdfIoTargetAllocAndQueryTargetProperty</b> method determines the amount of memory that is necessary to hold the requested device property. This method allocates enough memory to hold the data and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>.

For more information about <b>WdfIoTargetAllocAndQueryTargetProperty</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

The following code example calls <b>WdfIoTargetAllocAndQueryTargetProperty</b> to obtain the <b>DevicePropertyFriendlyName</b> property. After <b>WdfIoTargetAllocAndQueryTargetProperty</b> returns, the driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer that contains the name string.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandqueryproperty.md">WdfDeviceAllocAndQueryProperty</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetquerytargetproperty.md">WdfIoTargetQueryTargetProperty</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetAllocAndQueryTargetProperty method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

