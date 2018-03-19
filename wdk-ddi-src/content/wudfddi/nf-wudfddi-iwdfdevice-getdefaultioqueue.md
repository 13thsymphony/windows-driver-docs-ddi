---
UID: NF:wudfddi.IWDFDevice.GetDefaultIoQueue
title: IWDFDevice::GetDefaultIoQueue method
author: windows-driver-content
description: The GetDefaultIoQueue method retrieves the interface of the default I/O queue for a device.
old-location: wdf\iwdfdevice_getdefaultioqueue.htm
old-project: wdf
ms.assetid: 9e998e54-b4c9-41ed-bba8-6f11c013f681
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetDefaultIoQueue method, GetDefaultIoQueue method, IWDFDevice interface, GetDefaultIoQueue,IWDFDevice.GetDefaultIoQueue, IWDFDevice, IWDFDevice interface, GetDefaultIoQueue method, IWDFDevice::GetDefaultIoQueue, UMDFDeviceObjectRef_b4c10b3b-eba4-4e6c-8f9e-80c32705f43d.xml, umdf.iwdfdevice_getdefaultioqueue, wdf.iwdfdevice_getdefaultioqueue, wudfddi/IWDFDevice::GetDefaultIoQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice.GetDefaultIoQueue
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetDefaultIoQueue method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDefaultIoQueue</b> method retrieves the interface of the default I/O queue for a device.

## Syntax

````
void GetDefaultIoQueue(
  [out] IWDFIoQueue **ppWdfIoQueue
);
````

## Parameters

`ppWdfIoQueue`

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the default I/O queue object.


## Return Value

None

## Remarks

For more information about queue objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-i-o-queue-object">Framework I/O Queue Object</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>