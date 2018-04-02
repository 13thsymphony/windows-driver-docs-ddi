---
UID: NF:wudfddi.IRemoteInterfaceCallbackRemoval.OnRemoteInterfaceRemoval
title: IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval method
author: windows-driver-content
description: A UMDF-based driver's OnRemoteInterfaceRemoval event callback function notifies the driver that it cannot use a device interface because the interface has been removed.
old-location: wdf\iremoteinterfacecallbackremoval_onremoteinterfaceremoval.htm
old-project: wdf
ms.assetid: 0dfa2eb8-a7f6-46d9-9599-5e2aaf583f78
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IRemoteInterfaceCallbackRemoval, IRemoteInterfaceCallbackRemoval interface, OnRemoteInterfaceRemoval method, IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval, OnRemoteInterfaceRemoval method, OnRemoteInterfaceRemoval method, IRemoteInterfaceCallbackRemoval interface, OnRemoteInterfaceRemoval,IRemoteInterfaceCallbackRemoval.OnRemoteInterfaceRemoval, UMDFIoTargetObjectRef_17c1557c-2046-4bea-8b7f-88fea7103155.xml, umdf.iremoteinterfacecallbackremoval_onremoteinterfaceremoval, wdf.iremoteinterfacecallbackremoval_onremoteinterfaceremoval, wudfddi/IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IRemoteInterfaceCallbackRemoval.OnRemoteInterfaceRemoval
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A UMDF-based driver's <b>OnRemoteInterfaceRemoval</b> event callback function notifies the driver that it cannot use a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a> because the interface has been removed.

## Syntax

```
void OnRemoteInterfaceRemoval(
  IWDFRemoteInterface *pWdfRemoteInterface
);
```

## Parameters

`pWdfRemoteInterface`

A pointer to the <a href="https://msdn.microsoft.com/10d4cd20-c797-455c-b16d-00982be5c1b7">IWDFRemoteInterface</a> interface of a remote interface object that represents a device interface. The driver obtains this pointer when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a>.


## Return Value

None.

## Remarks

A driver's <b>OnRemoteInterfaceRemoval</b> event callback function must do whatever driver-specific tasks are necessary to handle removal of the device interface. In addition, the callback must delete the remote interface object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> created and call the interface's <b>Release</b> function if it has previously called the interface's <b>AddRef</b> function.

If the driver does not provide this callback function, the framework deletes the remote interface object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> created. 

For more information about a driver's <b>OnRemoteInterfaceRemoval</b> event callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556889">IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556891">IRemoteInterfaceCallbackRemoval</a>