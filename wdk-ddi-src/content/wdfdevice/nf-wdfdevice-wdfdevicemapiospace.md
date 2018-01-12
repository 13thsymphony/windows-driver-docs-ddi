---
UID: NF:wdfdevice.WdfDeviceMapIoSpace
title: WdfDeviceMapIoSpace function
author: windows-driver-content
description: The WdfDeviceMapIoSpace function maps the given physical address range to system address space and returns a pseudo base address.
old-location: wdf\wdfdevicemapiospace.htm
old-project: wdf
ms.assetid: 13ECF87D-13F7-4154-A17E-D49A2BB0F83A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfDeviceMapIoSpace
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
req.alt-api: WdfDeviceMapIoSpace
req.alt-loc: WUDFx02000.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceMapIoSpace function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceMapIoSpace</b> function maps the given physical address range to system address space and returns a pseudo base address.



## -syntax

````
NTSTATUS WdfDeviceMapIoSpace(
  _In_  WDFDEVICE           Device,
  _In_  PHYSICAL_ADDRESS    PhysicalAddress,
  _In_  SIZE_T              NumberOfBytes,
  _In_  MEMORY_CACHING_TYPE CacheType,
  _Out_ PVOID               *PseudoBaseAddress
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param PhysicalAddress [in]

Specifies the starting 64-bit physical address of the I/O range to be mapped.


### -param NumberOfBytes [in]

Specifies a value greater than zero, indicating the number of bytes to be mapped.


### -param CacheType [in]

Specifies a <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the physical address range. The MEMORY_CACHING_TYPE enumeration type is defined in Wdfdevice.h.


### -param PseudoBaseAddress [out]

The address of a location that receives a pointer to the pseudo base address.




## -returns
If the operation succeeds, the function returns STATUS_SUCCESS. 

The function might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
This function is the UMDF version 2 equivalent of <a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>.

A driver must call this function during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>WdfDeviceMapIoSpace</b> maps the physical address returned in the resource list to a framework-managed address referred to as the pseudo base address. 

 The driver can then use the pseudo base address to access device registers with WDF_READ_REGISTER_<i>Xxx</i> and WDF_WRITE_REGISTER_<i>Xxx</i> functions. 

A driver that calls <b>WdfDeviceMapIoSpace</b> must set the <b>UmdfDirectHardwareAccess</b> INF directive to <b>AllowDirectHardwareAccess</b>.

 If the driver sets the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>, calling <b>WdfDeviceMapIoSpace</b> also maps the given physical address range to a user-mode base address range that the driver can subsequently access by calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegethardwareregistermappedaddress.md">WdfDeviceGetHardwareRegisterMappedAddress</a>.

 For more information about  INF directives that UMDF drivers can use, see <a href="https://msdn.microsoft.com/aefc678e-dc81-47dc-a84b-f1a79c16cad9">Specifying WDF Directives in INF Files</a>.

For more information about parsing hardware resources starting in UMDF version 2, see <a href="wdf.handling_hardware_resources_in_a_umdf_driver">Handling Hardware Resources in a UMDF Driver</a>.

The PHYSICAL_ADDRESS type is defined in Wudfwdm.h, as follows:<pre class="syntax" xml:space="preserve"><code>typedef LARGE_INTEGER PHYSICAL_ADDRESS;</code></pre>


For an example that shows how a driver finds and maps memory-mapped register resources, see <a href="https://msdn.microsoft.com/58A94C75-94C1-4517-A300-9F04AA7B771A">Reading and Writing to Device Registers</a>.


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
<dt>WUDFx02000.dll</dt>
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
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceunmapiospace.md">WdfDeviceUnmapIoSpace</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceMapIoSpace function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

