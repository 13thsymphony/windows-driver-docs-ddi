---
UID: NF:wdm.IoWMIDeviceObjectToProviderId
title: IoWMIDeviceObjectToProviderId function
author: windows-driver-content
description: The IoWMIDeviceObjectToProviderId routine translates the specified device object into the corresponding WMI Provider ID.
old-location: kernel\iowmideviceobjecttoproviderid.htm
old-project: kernel
ms.assetid: 211d41ae-18d3-4ca5-b9f5-868d97fab6fb
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoWMIDeviceObjectToProviderId, IoWMIDeviceObjectToProviderId routine [Kernel-Mode Driver Architecture], k104_e24ce1c2-9f90-49b5-88be-1bbf40074aee.xml, kernel.iowmideviceobjecttoproviderid, wdm/IoWMIDeviceObjectToProviderId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoWMIDeviceObjectToProviderId
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoWMIDeviceObjectToProviderId function
The <b>IoWMIDeviceObjectToProviderId</b> routine translates the specified device object into the corresponding WMI Provider ID.

## Syntax

````
ULONG IoWMIDeviceObjectToProviderId(
  _In_ PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`DeviceObject`

Pointer to a device object.


## Return Value

<b>IoWMIDeviceObjectToProviderId </b>returns the WMI Provider ID associated with the specified device object.

## Remarks

<b>IoWMIDeviceObjectToProviderId</b> should be used when filling in the <b>ProviderId</b> member of the <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> structure in those cases when the <b>WNODEHEADER</b> structure is being initialized as part of a <a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a> or <a href="..\wmistr\ns-wmistr-tagwnode_event_reference.md">WNODE_EVENT_REFERENCE</a> structure. (If the <b>WNODE_HEADER</b> is being used for other purposes, <i>ProviderId</i> is reserved.)

When running on a 32-bit operating system, the provider ID and the device object are identical. When running on a 64-bit operating system, <b>IoWMIDeviceObjectToProviderId</b> will convert the 64-bit device object to a 32-bit provider ID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\wmistr\ns-wmistr-tagwnode_event_reference.md">WNODE_EVENT_REFERENCE</a>



<a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a>



<a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a>