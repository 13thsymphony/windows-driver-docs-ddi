---
UID: NF:storport.StorPortWriteRegisterUlong
title: StorPortWriteRegisterUlong function
author: windows-driver-content
description: The StorPortWriteRegisterUlong routine transfers a ULONG value to the indicated HBA register address.
old-location: storage\storportwriteregisterulong.htm
old-project: storage
ms.assetid: 12ed5f88-26af-43a4-82c7-5f36d9388cc8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortWriteRegisterUlong, StorPortWriteRegisterUlong routine [Storage Devices], storprt_64890de0-32e7-4e07-bcbc-35a11acd6896.xml, StorPortWriteRegisterUlong, storage.storportwriteregisterulong
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
-	StorPortWriteRegisterUlong
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortWriteRegisterUlong function
The <b>StorPortWriteRegisterUlong</b> routine transfers a ULONG value to the indicated HBA register address.

## Syntax

````
STORPORT_API VOID StorPortWriteRegisterUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Register,
  _In_ ULONG  Value
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory space range returned by <a href="..\storport\nf-storport-storportgetdevicebase.md">StorPortGetDeviceBase</a>.

`Value`

Specifies the ULONG value to be written to the HBA's register.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportwriteregisterulong.md">ScsiPortWriteRegisterUlong</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWriteRegisterUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>