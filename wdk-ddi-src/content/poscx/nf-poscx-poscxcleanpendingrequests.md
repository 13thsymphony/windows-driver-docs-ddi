---
UID: NF:poscx.PosCxCleanPendingRequests
title: PosCxCleanPendingRequests function
author: windows-driver-content
description: PosCxCleanPendingRequests is called to cancel all pending requests for a given caller, identified by the open instance.
old-location: pos\poscxcleanpendingrequests.htm
old-project: pos
ms.assetid: FD6036D5-C316-43E6-8C37-067F5705BCB6
ms.author: windowsdriverdev
ms.date: 2/19/2018
ms.keywords: pos.poscxcleanpendingrequests, PosCxCleanPendingRequests, poscx/PosCxCleanPendingRequests, PosCxCleanPendingRequests function
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	PosCxCleanPendingRequests
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---


# PosCxCleanPendingRequests function
PosCxCleanPendingRequests is called to cancel all pending requests for a given  

      caller, identified by the open instance.

## Syntax

````
VOID PosCxCleanPendingRequests(
  _In_     WDFDEVICE     device,
  _In_opt_ WDFFILEOBJECT callerFileObj,
  _In_     NTSTATUS      completionStatus
);
````

## Parameters

`device`

A handle to a framework device object that represents the device.

`callerFileObj`

A handle to a framework file object for which all pending requests should be 

          cancelled, or NULL to cancel all pending requests.

`completionStatus`

An appropriate NTSTATUS error code that indicates success or failure.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | poscx.h (include Poscx.h) |
| **Library** | NtosKrnl.exe |