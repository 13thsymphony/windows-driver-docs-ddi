---
UID: NF.ndis.NdisRegisterDeviceEx
title: NdisRegisterDeviceEx function
author: windows-driver-content
description: The NdisRegisterDeviceEx function creates a device object that is based upon the specified attributes.
old-location: netvista\ndisregisterdeviceex.htm
old-project: NetVista
ms.assetid: 8e0d406e-748c-4b37-90fb-c7b9dfc28362
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisRegisterDeviceEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisRegisterDeviceEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisRegisterDeviceEx function



## -description
The 
  <b>NdisRegisterDeviceEx</b> function creates a device object that is based upon the specified
  attributes.



## -syntax

````
NDIS_STATUS NdisRegisterDeviceEx(
  _In_  NDIS_HANDLE                    NdisHandle,
  _In_  PNDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes,
  _Out_ PDEVICE_OBJECT                 *pDeviceObject,
  _Out_ PNDIS_HANDLE                   NdisDeviceHandle
);
````


## -parameters

### -param NdisHandle [in]

A miniport driver handle or filter driver handle that the caller obtained by calling the 
     <a href="netvista.ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function or the 
     <a href="netvista.ndisfregisterfilterdriver">
     NdisFRegisterFilterDriver</a> function respectively.


### -param DeviceObjectAttributes [in]

A pointer to an 
     <a href="netvista.ndis_device_object_attributes">
     NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure that contains the attributes for the new device.


### -param pDeviceObject [out]

A pointer that points to a pointer to a newly created 
     <a href="kernel.device_object">DEVICE_OBJECT</a> structure, if the call succeeds.
     If the call fails, 
     <i>pDeviceObject</i> is set to point to <b>NULL</b>.


### -param NdisDeviceHandle [out]

A pointer to a caller-supplied variable in which this function, if it succeeds, returns a handle
     to the device object. This handle is a required parameter to the 
     <a href="netvista.ndisderegisterdeviceex">NdisDeregisterDeviceEx</a> function
     that the driver calls subsequently.


## -returns
<b>NdisRegisterDeviceEx</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><b>NdisRegisterDeviceEx</b> successfully registered the device.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>The caller is not an NDIS driver.
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i> or NTSTATUS_<i>XXX</i></b></dt>
</dl>The driver's attempt to register the device failed. Usually, such an error status is propagated
       from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.

 


## -remarks
Miniport drivers and filter drivers can call 
    <b>NdisRegisterDeviceEx</b> to register a virtual device.

If an NDIS driver requires space for context information in the device object, the driver can pass a
    nonzero value for the 
    <b>ExtensionSize</b> member in the 
    <a href="netvista.ndis_device_object_attributes">
    NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure at the 
    <i>DeviceObjectAttributes</i> parameter. In this case, NDIS allocates the extension for the driver, and
    the driver can call the 
    <a href="netvista.ndisgetdevicereservedextension">
    NdisGetDeviceReservedExtension</a> function to get a pointer to the extension.

The driver must subsequently call the 
    <a href="netvista.ndisderegisterdeviceex">NdisDeregisterDeviceEx</a> function
    when the device is no longer needed. If 
    <b>NdisRegisterDeviceEx</b> allocated an extension, 
    <b>NdisDeregisterDeviceEx</b> frees the extension.


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
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="netvista.ndis_device_object_attributes">NDIS_DEVICE_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.ndisderegisterdeviceex">NdisDeregisterDeviceEx</a>
</dt>
<dt>
<a href="netvista.ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="netvista.ndisgetdevicereservedextension">
   NdisGetDeviceReservedExtension</a>
</dt>
<dt>
<a href="netvista.ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisRegisterDeviceEx function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

