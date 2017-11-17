---
UID: NF.ndis.NdisRegisterDeviceEx
title: NdisRegisterDeviceEx
author: windows-driver-content
description: The NdisRegisterDeviceEx function creates a device object that is based upon the specified attributes.
old-location: netvista\ndisregisterdeviceex.htm
ms.assetid: 8e0d406e-748c-4b37-90fb-c7b9dfc28362
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
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
ms.keywords: NdisRegisterDeviceEx
req.iface: 
---

# NdisRegisterDeviceEx function



## -description
<p>The 
  <b>NdisRegisterDeviceEx</b> function creates a device object that is based upon the specified
  attributes.</p>


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
<dl>

### -param <i>NdisHandle</i> [in]

<dd>
<p>A miniport driver handle or filter driver handle that the caller obtained by calling the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> function or the 
     <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
     NdisFRegisterFilterDriver</a> function respectively.</p>
</dd>

### -param <i>DeviceObjectAttributes</i> [in]

<dd>
<p>A pointer to an 
     <a href="https://msdn.microsoft.com/658e1597-eacf-4e9e-9f10-37f7646d38ad">
     NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure that contains the attributes for the new device.</p>
</dd>

### -param <i>pDeviceObject</i> [out]

<dd>
<p>A pointer that points to a pointer to a newly created 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure, if the call succeeds.
     If the call fails, 
     <i>pDeviceObject</i> is set to point to <b>NULL</b>.</p>
</dd>

### -param <i>NdisDeviceHandle</i> [out]

<dd>
<p>A pointer to a caller-supplied variable in which this function, if it succeeds, returns a handle
     to the device object. This handle is a required parameter to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561741">NdisDeregisterDeviceEx</a> function
     that the driver calls subsequently.</p>
</dd>
</dl>

## -returns
<p><b>NdisRegisterDeviceEx</b> returns one of the following status values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p><b>NdisRegisterDeviceEx</b> successfully registered the device.</p><dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl><p>The caller is not an NDIS driver.</p><dl>
<dt><b>NDIS_STATUS_<i>XXX</i> or NTSTATUS_<i>XXX</i></b></dt>
</dl><p>The driver's attempt to register the device failed. Usually, such an error status is propagated
       from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.</p>

<p> </p>

## -remarks
<p>Miniport drivers and filter drivers can call 
    <b>NdisRegisterDeviceEx</b> to register a virtual device.</p>

<p>If an NDIS driver requires space for context information in the device object, the driver can pass a
    nonzero value for the 
    <b>ExtensionSize</b> member in the 
    <a href="https://msdn.microsoft.com/658e1597-eacf-4e9e-9f10-37f7646d38ad">
    NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure at the 
    <i>DeviceObjectAttributes</i> parameter. In this case, NDIS allocates the extension for the driver, and
    the driver can call the 
    <a href="https://msdn.microsoft.com/6b2c56a9-cf77-4734-8f85-0ca740084ce3">
    NdisGetDeviceReservedExtension</a> function to get a pointer to the extension.</p>

<p>The driver must subsequently call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561741">NdisDeregisterDeviceEx</a> function
    when the device is no longer needed. If 
    <b>NdisRegisterDeviceEx</b> allocated an extension, 
    <b>NdisDeregisterDeviceEx</b> frees the extension.</p>

<p>Miniport drivers and filter drivers can call 
    <b>NdisRegisterDeviceEx</b> to register a virtual device.</p>

<p>If an NDIS driver requires space for context information in the device object, the driver can pass a
    nonzero value for the 
    <b>ExtensionSize</b> member in the 
    <a href="https://msdn.microsoft.com/658e1597-eacf-4e9e-9f10-37f7646d38ad">
    NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure at the 
    <i>DeviceObjectAttributes</i> parameter. In this case, NDIS allocates the extension for the driver, and
    the driver can call the 
    <a href="https://msdn.microsoft.com/6b2c56a9-cf77-4734-8f85-0ca740084ce3">
    NdisGetDeviceReservedExtension</a> function to get a pointer to the extension.</p>

<p>The driver must subsequently call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561741">NdisDeregisterDeviceEx</a> function
    when the device is no longer needed. If 
    <b>NdisRegisterDeviceEx</b> allocated an extension, 
    <b>NdisDeregisterDeviceEx</b> frees the extension.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547982">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565426">NDIS_DEVICE_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561741">NdisDeregisterDeviceEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6b2c56a9-cf77-4734-8f85-0ca740084ce3">
   NdisGetDeviceReservedExtension</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRegisterDeviceEx function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
