---
UID: NF.wdfdevice.WdfDeviceAllocAndQueryInterfaceProperty
title: WdfDeviceAllocAndQueryInterfaceProperty function
author: windows-driver-content
description: The WdfDeviceAllocAndQueryInterfaceProperty method allocates a buffer and retrieves a specified device interface property.
old-location: wdf\wdfdeviceallocandqueryinterfaceproperty.htm
old-project: wdf
ms.assetid: 40516E83-892C-4538-B452-DAB0F5ACBB25
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDeviceAllocAndQueryInterfaceProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WdfDeviceAllocAndQueryInterfaceProperty
req.alt-loc: WUDFx02000.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfDeviceAllocAndQueryInterfaceProperty function



## -description
<p class="CCE_Message">[Applies to UMDF only]
The <b>WdfDeviceAllocAndQueryInterfaceProperty</b> method  allocates a buffer and retrieves a specified device interface property.


## -syntax

````
NTSTATUS WdfDeviceAllocAndQueryInterfaceProperty(
  _In_     WDFDEVICE                           Device,
  _In_     PWDF_DEVICE_INTERFACE_PROPERTY_DATA PropertyData,
  _In_     POOL_TYPE                           PoolType,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES              PropertyMemoryAttributes,
  _Out_    WDFMEMORY                           PropertyMemory,
  _Out_    PDEVPROPTYPE                        Type
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.

### -param PropertyData [in]

A pointer to a <a href="wdf.wdf_device_interface_property_data">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure that identifies the device interface property to be retrieved.

### -param PoolType [in]

A <b>POOL_TYPE</b>-typed enumerator that specifies the type of memory to be allocated.

### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param PropertyMemory [out]

A pointer to a <b>WDFMEMORY</b>-typed location that receives a handle to a framework memory object.



### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b>-typed variable that, on return,  identifies the type of property data contained in <i>PropertyMemory</i>.

## -returns
If the <b>WdfDeviceAllocAndQueryInterfaceProperty</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One of the parameters is incorrect.

 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## -remarks
The <b>WdfDeviceAllocAndQueryInterfaceProperty</b> method determines the amount of memory that is necessary to hold the requested device interface property. It allocates enough memory to hold the data, and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="wdf.wdfmemorygetbuffer">WdfMemoryGetBuffer</a>. 

For information about related methods, see <a href="wdf.accessing_the_unified_device_property_model">Accessing the Unified Device Property Model</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum support
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>WUDFx02000.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>WUDFx02000.dll; </dt>
<dt>TBD</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_device_interface_property_data">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a>
</dt>
<dt>
<a href="wdf.wdf_device_interface_property_data_init">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>
</dt>
<dt>
<a href="wdf.wdfdeviceassigninterfaceproperty">WdfDeviceAssignInterfaceProperty</a>
</dt>
<dt>
<a href="wdf.wdfdevicequeryinterfaceproperty">WdfDeviceQueryInterfaceProperty</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAllocAndQueryInterfaceProperty method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
