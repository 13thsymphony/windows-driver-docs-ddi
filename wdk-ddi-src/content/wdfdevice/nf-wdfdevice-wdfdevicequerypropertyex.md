---
UID: NF:wdfdevice.WdfDeviceQueryPropertyEx
title: WdfDeviceQueryPropertyEx function
author: windows-driver-content
description: The WdfDeviceQueryPropertyEx method retrieves a specified device property.
old-location: wdf\wdfdevicequerypropertyex.htm
old-project: wdf
ms.assetid: CA189010-0BEB-420A-BE69-5F7FEE322FE3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDeviceQueryPropertyEx, WdfDeviceQueryPropertyEx method, wdf.wdfdevicequerypropertyex, wdfdevice/WdfDeviceQueryPropertyEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: APC_LEVEL
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
-	WdfDeviceQueryPropertyEx
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceQueryPropertyEx function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceQueryPropertyEx</b> method retrieves a specified device property.

## Syntax

````
NTSTATUS WdfDeviceQueryPropertyEx(
  _In_  WDFDEVICE                 Device,
  _In_  PWDF_DEVICE_PROPERTY_DATA DeviceProperty,
  _In_  ULONG                     BufferLength,
  _Out_ PVOID                     PropertyBuffer,
  _Out_ PULONG                    RequiredSize,
  _Out_ PDEVPROPTYPE              Type
);
````

## Parameters

`Device`

A handle to a framework device object.

`DeviceProperty`

A pointer to a <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_property_data.md">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to be retrieved.

`BufferLength`

The size, in bytes, of the buffer that is pointed to by <i>PropertyBuffer</i>.

`PropertyBuffer`

A caller-supplied pointer to a caller-allocated buffer that receives the requested information. The pointer can be <b>NULL</b> if the <i>BufferLength</i> parameter is zero.

`RequiredSize`

A caller-supplied location that, on return, contains the size, in bytes, of the information that the method stored in <i>PropertyBuffer</i>. If the function's return value is <b>STATUS_BUFFER_TOO_SMALL</b>, this location receives the required buffer size.

`Type`

A pointer to a <b>DEVPROPTYPE</b> variable. If the method is successful, upon return this parameter contains the property type value
                  of the property 
                  data stored in <i>PropertyBuffer</i>.


## Return Value

If the operation succeeds, <b>WdfDeviceQueryPropertyEx</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The supplied buffer is too small to receive the information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>DeviceProperty</i> value is invalid.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

You can use <b>WdfDeviceQueryPropertyEx</b> to retrieve any property that is exposed through the unified property model, whereas the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryproperty.md">WdfDeviceQueryProperty</a> method only allows querying a subset of the unified property model.

Before receiving device property data, drivers typically call the <b>WdfDeviceQueryPropertyEx</b> method just to obtain the required buffer size. For some properties, the data size can change between when the required size is returned and when the driver calls <b>WdfDeviceQueryPropertyEx</b> again. Therefore, drivers should call <b>WdfDeviceQueryPropertyEx</b> inside a loop that executes until the return status is not STATUS_BUFFER_TOO_SMALL. 

It is best to use <b>WdfDeviceQueryPropertyEx</b> only if the required buffer size is known and unchanging, because in that case the driver has to call <b>WdfDeviceQueryPropertyEx</b> only once. If the required buffer size is unknown or varies, the driver should call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceallocandquerypropertyex.md">WdfDeviceAllocAndQueryPropertyEx</a>. 

For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | APC_LEVEL |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryinterfaceproperty.md">WdfDeviceQueryInterfaceProperty</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryproperty.md">WdfDeviceQueryProperty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceQueryPropertyEx method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>