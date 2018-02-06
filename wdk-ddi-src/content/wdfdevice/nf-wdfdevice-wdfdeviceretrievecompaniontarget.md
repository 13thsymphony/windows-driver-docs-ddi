---
UID: NF:wdfdevice.WdfDeviceRetrieveCompanionTarget
title: WdfDeviceRetrieveCompanionTarget function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfdeviceretrievecompaniontarget.htm
old-project: wdf
ms.assetid: 2ca34fb7-72c1-4253-ad5b-bc829a1ba540
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfdeviceretrievecompaniontarget, WdfDeviceRetrieveCompanionTarget, wdfdevice/WdfDeviceRetrieveCompanionTarget, WdfDeviceRetrieveCompanionTarget method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WdfDeviceRetrieveCompanionTarget
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceRetrieveCompanionTarget function
For internal use only.

## Syntax

````
NTSTATUS WdfDeviceRetrieveCompanionTarget(
  _In_  WDFDEVICE          Device,
  _Out_ WDFCOMPANIONTARGET *CompanionTarget
);
````

## Parameters

`Device`



`CompanionTarget`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.23 |
| **Header** | wdfdevice.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |