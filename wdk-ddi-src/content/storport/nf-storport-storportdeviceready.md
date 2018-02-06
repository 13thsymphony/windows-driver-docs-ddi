---
UID: NF:storport.StorPortDeviceReady
title: StorPortDeviceReady function
author: windows-driver-content
description: The StorPortDeviceReady routine notifies the port driver that the indicated logical unit is ready to handle new requests.
old-location: storage\storportdeviceready.htm
old-project: storage
ms.assetid: 6dd3abdb-9037-4cf5-abe7-7776dcf67bd5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortDeviceReady, storage.storportdeviceready, StorPortDeviceReady, StorPortDeviceReady routine [Storage Devices], storprt_18a6f185-17dd-446c-9bbe-3937e1003a6b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortDeviceReady
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortDeviceReady function
The <b>StorPortDeviceReady</b> routine notifies the port driver that the indicated logical unit is ready to handle new requests.

## Syntax

````
STORPORT_API BOOLEAN StorPortDeviceReady(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`PathId`

Identifies the SCSI bus.

`TargetId`

Identifies the target controller or device on the given buses.

`Lun`

Identifies the logical unit for the given target controller or device.


## Return Value

<b>StorPortDeviceReady</b> returns <b>TRUE</b> if the miniport driver succeeded in notifying the port driver, <b>FALSE</b> if not.

## Remarks

It is not generally necessary to notify the target device that new requests are required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-storportdevicebusy.md">StorPortDeviceBusy</a>

<a href="..\storport\nf-storport-storportready.md">StorPortReady</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortDeviceReady routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>