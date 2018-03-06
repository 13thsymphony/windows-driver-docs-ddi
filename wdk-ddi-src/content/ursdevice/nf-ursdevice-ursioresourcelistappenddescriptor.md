---
UID: NF:ursdevice.UrsIoResourceListAppendDescriptor
title: UrsIoResourceListAppendDescriptor function
author: windows-driver-content
description: Appends the specified resource descriptor to the specified I/O resource list object that maintains resource descriptors for the host or function role.
old-location: buses\ursioresourcelistappenddescriptor.htm
old-project: usbref
ms.assetid: 80AE8211-EA8F-4967-A496-39053CD578D1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UrsIoResourceListAppendDescriptor, UrsIoResourceListAppendDescriptor function [Buses], buses.ursioresourcelistappenddescriptor, ursdevice/UrsIoResourceListAppendDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Urscxstub.lib
-	Urscxstub.dll
api_name:
-	UrsIoResourceListAppendDescriptor
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---


# UrsIoResourceListAppendDescriptor function
Appends the specified resource descriptor to the specified I/O resource list object that maintains resource descriptors for the
    host or function role.

## Syntax

````
FORCEINLINE NTSTATUS UrsIoResourceListAppendDescriptor(
  _In_ URSIORESLIST            IoResourceList,
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor
);
````

## Parameters

`IoResourceList`

A role's I/O resource list object to which the resource descriptor is appended. This object is allocated by the framework and passed to the client driver when the framework invokes the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> implementation.

`Descriptor`

A pointer to  IO_RESOURCE_DESCRIPTOR that contains the resource descriptor for the role.


## Return Value

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

After the client driver calls <a href="..\ursdevice\nf-ursdevice-ursdeviceinitialize.md">UrsDeviceInitialize</a>, the framework allocates memory for the <i>resource requirements list</i>. When the USB dual-role class extension  invokes the client driver's implementation of <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>, it passes a WDFIORESREQLIST handle to that requirements list along with URSIORESLIST handles for host and function role <i>resource lists</i>. In the implementation, the client driver is expected to enumerate through the requirements list and add the resource descriptor (if it wants to use that resource)  to the resource list for each role.

To add a resource descriptors for a role, the driver calls <b>UrsIoResourceListAppendDescriptor</b> and specifies the descriptor and the resource list to which the resource must be added. 

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Handling Hardware Resources</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | ursdevice.h (include Urscx.h) |
| **Library** | Urscxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ursdevice\nf-ursdevice-ursdeviceinitialize.md">UrsDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UrsIoResourceListAppendDescriptor function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>