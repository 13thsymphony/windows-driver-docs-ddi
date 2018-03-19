---
UID: NF:wdfdevice.WdfDeviceCreateDeviceInterface
title: WdfDeviceCreateDeviceInterface function
author: windows-driver-content
description: The WdfDeviceCreateDeviceInterface method creates a device interface for a specified device.
old-location: wdf\wdfdevicecreatedeviceinterface.htm
old-project: wdf
ms.assetid: cdfe1932-ee3d-41ea-8d7b-85c17c0f1722
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_467c4866-4ba7-4450-9aec-e63c3172d604.xml, WdfDeviceCreateDeviceInterface, WdfDeviceCreateDeviceInterface method, kmdf.wdfdevicecreatedeviceinterface, wdf.wdfdevicecreatedeviceinterface, wdfdevice/WdfDeviceCreateDeviceInterface
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
-	WdfDeviceCreateDeviceInterface
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceCreateDeviceInterface function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceCreateDeviceInterface</b> method creates a device interface for a specified device.

## Syntax

````
NTSTATUS WdfDeviceCreateDeviceInterface(
  _In_           WDFDEVICE        Device,
  _In_     const GUID             *InterfaceClassGUID,
  _In_opt_       PCUNICODE_STRING ReferenceString
);
````

## Parameters

`Device`

A handle to a framework device object.

`InterfaceClassGUID`

A pointer to a GUID that identifies the device interface class.

`ReferenceString`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that describes a reference string for the device interface. The string must not contain any path separator characters ("/" or "\").  This parameter is optional and can be <b>NULL</b>.   For more information, see the following Remarks section.


## Return Value

<b>WdfDeviceCreateDeviceInterface</b> returns STATUS_SUCCESS if the operation succeeds.

For a list of other return values that <b>WdfDeviceCreateDeviceInterface</b> can return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Drivers can use the <i>ReferenceString</i> parameter to differentiate different instances of a single interface. In other words, if a driver calls <b>WdfDeviceCreateDeviceInterface</b> twice for the same device interface class, the driver can specify a different <i>ReferenceString</i> parameter each time. When an instance of an interface is opened, the I/O manager passes the instance's reference string to the driver. The reference string is appended to the path component of the interface instance's name. The driver can then use the reference string to determine which instance of the device interface class is being opened.

For more information about device interfaces and the <b>WdfDeviceCreateDeviceInterface</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces">Using Device Interfaces</a>.


#### Examples

The following example registers the COM port interface class for a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;

status = WdfDeviceCreateDeviceInterface(
                                        Device,
                                        (LPGUID) &amp;GUID_DEVINTERFACE_COMPORT,
                                        NULL
                                        );</pre>
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

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md">WdfDeviceSetDeviceInterfaceState</a>