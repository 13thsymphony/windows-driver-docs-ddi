---
UID: NF:d3dkmthk.D3DKMTSubmitSignalSyncObjectsToHwQueue
title: D3DKMTSubmitSignalSyncObjectsToHwQueue function
author: windows-driver-content
description: Used to submit a signal to the hardware queue.
old-location: display\d3dkmtsubmitsignalsyncobjectstohwqueue.htm
old-project: display
ms.assetid: DA0D44AF-168F-4B9B-B184-1DC8C3477CBC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTSubmitSignalSyncObjectsToHwQueue, d3dkmthk/D3DKMTSubmitSignalSyncObjectsToHwQueue, D3DKMTSubmitSignalSyncObjectsToHwQueue function [Display Devices], display.d3dkmtsubmitsignalsyncobjectstohwqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
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
req.lib: Tbd
req.dll: Tbd
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	tbd
apiname:
-	D3DKMTSubmitSignalSyncObjectsToHwQueue
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTSubmitSignalSyncObjectsToHwQueue function
Used to submit a signal to the hardware queue.

## Syntax

````
NTSTATUS APIENTRY D3DKMTSubmitSignalSyncObjectsToHwQueue(
  _In_ const D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE *submitWaitForSyncObjectsToHwQueue
);
````

## Parameters

`D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE`

TBD


## Return Value

Returns STATUS_SUCCESS if called successfully.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3dkmthk.h |
| **Library** | Tbd |
| **DLL** | Tbd |