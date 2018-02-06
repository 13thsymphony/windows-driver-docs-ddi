---
UID: NF:wdfdevice.WdfDeviceAssignInterfaceProperty
title: WdfDeviceAssignInterfaceProperty function
author: windows-driver-content
description: The WdfDeviceAssignInterfaceProperty method modifies the current value of a device interface property.
old-location: wdf\wdfdeviceassigninterfaceproperty.htm
old-project: wdf
ms.assetid: 49608EE6-1666-4430-AD22-9627EEF6F223
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICEASSIGNINTERFACEPROPERTY, WdfDeviceAssignInterfaceProperty, WdfDeviceAssignInterfaceProperty method, wdfdevice/WdfDeviceAssignInterfaceProperty, wdf.wdfdeviceassigninterfaceproperty
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WUDFx02000.dll
apiname:
-	WdfDeviceAssignInterfaceProperty
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceAssignInterfaceProperty function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceAssignInterfaceProperty</b> method modifies the current value of a <a href="https://msdn.microsoft.com/43aa0ce6-a06b-43e4-a213-300554391ae0">device interface property</a>.

## Syntax

````
NTSTATUS WdfDeviceAssignInterfaceProperty(
  _In_     WDFDEVICE                           Device,
  _In_     PWDF_DEVICE_INTERFACE_PROPERTY_DATA PropertyData,
  _In_     DEVPROPTYPE                         Type,
  _In_     ULONG                               BufferLength,
  _In_opt_ PVOID                               PropertyBuffer
);
````

## Parameters

`Device`

A handle to a framework device object.

`PropertyData`

A pointer to <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_interface_property_data.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure.

`Type`

A <b>DEVPROPTYPE</b>-typed value that specifies the type of the data that is provided in <i>PropertyBuffer</i>.

`BufferLength`

Specifies the length, in bytes, of the buffer that <i>PropertyBuffer</i> points to.

`PropertyBuffer`

A pointer to the device interface property data. Set this parameter to <b>NULL</b> to delete the specified property.


## Return Value

If the <b>WdfDeviceAssignInterfaceProperty</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is incorrect.

</td>
</tr>
</table> 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | WUDFx02000.lib |
| **DLL** | WUDFx02000.dll; TBD |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryinterfaceproperty.md">WdfDeviceQueryInterfaceProperty</a>

<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_interface_property_data.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty.md">WdfDeviceAllocAndQueryInterfaceProperty</a>

<a href="..\wdfdevice\nf-wdfdevice-wdf_device_interface_property_data_init.md">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAssignInterfaceProperty method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>