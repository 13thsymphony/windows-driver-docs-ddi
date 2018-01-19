---
UID : NF:wdfdevice.WdfDeviceMapIoSpace
title : WdfDeviceMapIoSpace function
author : windows-driver-content
description : The WdfDeviceMapIoSpace function maps the given physical address range to system address space and returns a pseudo base address.
old-location : wdf\wdfdevicemapiospace.htm
old-project : wdf
ms.assetid : 13ECF87D-13F7-4154-A17E-D49A2BB0F83A
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDeviceMapIoSpace
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 2.0
req.alt-api : WdfDeviceMapIoSpace
req.alt-loc : WUDFx02000.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : WUDFx02000.lib
req.dll : WUDFx02000.dll
req.irql : PASSIVE_LEVEL
req.typenames : WDF_STATE_NOTIFICATION_TYPE
req.product : Windows 10 or later.
---


# WdfDeviceMapIoSpace function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceMapIoSpace</b> function maps the given physical address range to system address space and returns a pseudo base address.

## Syntax

````
NTSTATUS WdfDeviceMapIoSpace(
  _In_  WDFDEVICE           Device,
  _In_  PHYSICAL_ADDRESS    PhysicalAddress,
  _In_  SIZE_T              NumberOfBytes,
  _In_  MEMORY_CACHING_TYPE CacheType,
  _Out_ PVOID               *PseudoBaseAddress
);
````

## Parameters

`Device`

A handle to a framework device object.

`PhysicalAddress`

Specifies the starting 64-bit physical address of the I/O range to be mapped.

`NumberOfBytes`

Specifies a value greater than zero, indicating the number of bytes to be mapped.

`CacheType`

Specifies a <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the physical address range. The MEMORY_CACHING_TYPE enumeration type is defined in Wdfdevice.h.

`PseudoBaseAddress`

The address of a location that receives a pointer to the pseudo base address.


## Return Value

If the operation succeeds, the function returns STATUS_SUCCESS. 

The function might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

This function is the UMDF version 2 equivalent of <a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>.

A driver must call this function during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>WdfDeviceMapIoSpace</b> maps the physical address returned in the resource list to a framework-managed address referred to as the pseudo base address. 

 The driver can then use the pseudo base address to access device registers with WDF_READ_REGISTER_<i>Xxx</i> and WDF_WRITE_REGISTER_<i>Xxx</i> functions. 

A driver that calls <b>WdfDeviceMapIoSpace</b> must set the <b>UmdfDirectHardwareAccess</b> INF directive to <b>AllowDirectHardwareAccess</b>.

 If the driver sets the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>, calling <b>WdfDeviceMapIoSpace</b> also maps the given physical address range to a user-mode base address range that the driver can subsequently access by calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegethardwareregistermappedaddress.md">WdfDeviceGetHardwareRegisterMappedAddress</a>.

 For more information about  INF directives that UMDF drivers can use, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.

For more information about parsing hardware resources starting in UMDF version 2, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Hardware Resources in a UMDF Driver</a>.

The PHYSICAL_ADDRESS type is defined in Wudfwdm.h, as follows:<pre class="syntax" xml:space="preserve"><code>typedef LARGE_INTEGER PHYSICAL_ADDRESS;</code></pre>


For an example that shows how a driver finds and maps memory-mapped register resources, see <a href="https://msdn.microsoft.com/58A94C75-94C1-4517-A300-9F04AA7B771A">Reading and Writing to Device Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceunmapiospace.md">WdfDeviceUnmapIoSpace</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceMapIoSpace function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>