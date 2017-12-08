---
UID: NF.wdfiotarget.WdfIoTargetQueryTargetProperty
title: WdfIoTargetQueryTargetProperty function
author: windows-driver-content
description: The WdfIoTargetQueryTargetProperty method retrieves a specified device property for a specified I/O target.
old-location: wdf\wdfiotargetquerytargetproperty.htm
old-project: wdf
ms.assetid: 00987914-9fe2-4245-b463-ef362e31679d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfIoTargetQueryTargetProperty
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
req.alt-api: WdfIoTargetQueryTargetProperty
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
req.product: Windows 10 or later.
---

# WdfIoTargetQueryTargetProperty function



## -description
<p class="CCE_Message">[Applies to KMDF only]
The <b>WdfIoTargetQueryTargetProperty</b> method retrieves a specified device property for a specified I/O target.


## -syntax

````
NTSTATUS WdfIoTargetQueryTargetProperty(
  _In_      WDFIOTARGET              IoTarget,
  _In_      DEVICE_REGISTRY_PROPERTY DeviceProperty,
  _In_      ULONG                    BufferLength,
  _Out_opt_ PVOID                    PropertyBuffer,
  _Out_     PULONG                   ResultLength
);
````


## -parameters

### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="wdf.wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="wdf.wdfiotargetcreate">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.

### -param DeviceProperty [in]

A <a href="kernel.device_registry_property">DEVICE_REGISTRY_PROPERTY</a>-typed value that identifies the device property to be retrieved.

### -param BufferLength [in]

The size, in bytes, of the buffer that <i>PropertyBuffer</i> points to.

### -param PropertyBuffer [out, optional]

A pointer to a caller-allocated buffer that receives the requested device property information. This pointer can be <b>NULL</b> if <i>BufferLength</i> is zero.

### -param ResultLength [out]

A pointer to a location that, on return, contains the size, in bytes, of the information that <b>WdfIoTargetQueryTargetProperty</b> stored in the buffer that <i>PropertyBuffer</i> points to. If <b>WdfIoTargetQueryTargetProperty</b> returns STATUS_BUFFER_TOO_SMALL, this location receives the required buffer size.

## -returns
<b>WdfIoTargetQueryTargetProperty</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer that the <i>PropertyBuffer</i> parameter pointed to was too small to receive the requested information.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>The value that the <i>DeviceProperty</i> parameter specified was invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The device's drivers have not yet reported the device's properties.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
Before drivers receive device property data, they typically call the <b>WdfIoTargetQueryTargetProperty</b> method to obtain the required buffer size. For some properties, the data size can change between when the required size is returned and when the driver calls <b>WdfIoTargetQueryTargetProperty</b> again. Therefore, drivers should call <b>WdfIoTargetQueryTargetProperty</b> inside a loop that executes until the return status is not STATUS_BUFFER_TOO_SMALL. 

Instead of calling <b>WdfIoTargetQueryTargetProperty</b>, your driver can call <a href="wdf.wdfiotargetallocandquerytargetproperty">WdfIoTargetAllocAndQueryTargetProperty</a>, which allocates a buffer and places the property information in the buffer. 

For more information about <b>WdfIoTargetQueryTargetProperty</b>, see <a href="wdf.obtaining_information_about_a_general_i_o_target">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="wdf.using_i_o_targets">Using I/O Targets</a>.

The following code example obtains a device's <b>DevicePropertyUINumber</b> property. The example calls <b>WdfIoTargetQueryTargetProperty</b> instead of <a href="wdf.wdfiotargetallocandquerytargetproperty">WdfIoTargetAllocAndQueryTargetProperty</a> because the length of a UI number is known.

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
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfiotarget.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
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
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_registry_property">DEVICE_REGISTRY_PROPERTY</a>
</dt>
<dt>
<a href="wdf.wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>
</dt>
<dt>
<a href="wdf.wdfdevicequeryproperty">WdfDeviceQueryProperty</a>
</dt>
<dt>
<a href="wdf.wdfiotargetallocandquerytargetproperty">WdfIoTargetAllocAndQueryTargetProperty</a>
</dt>
<dt>
<a href="wdf.wdfiotargetcreate">WdfIoTargetCreate</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetQueryTargetProperty method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
