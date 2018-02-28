---
UID: NF:ks.KsCreateClock
title: KsCreateClock function
author: windows-driver-content
description: The KsCreateClock function creates a handle to a clock instance.
old-location: stream\kscreateclock.htm
old-project: stream
ms.assetid: a125161d-c086-45a4-9b66-4c13d9ed5f11
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsCreateClock, KsCreateClock function [Streaming Media Devices], ks/KsCreateClock, ksfunc_ba840ce8-a1c9-4ede-8d2e-6e2829ad9b11.xml, stream.kscreateclock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ks.lib
-	ks.dll
api_name:
-	KsCreateClock
product: Windows
targetos: Windows
req.typenames: 
---


# KsCreateClock function
The <b>KsCreateClock</b> function creates a handle to a clock instance.

## Syntax

````
NTSTATUS KsCreateClock(
  _In_  HANDLE          ConnectionHandle,
  _In_  PKSCLOCK_CREATE ClockCreate,
  _Out_ PHANDLE         ClockHandle
);
````

## Parameters

`ConnectionHandle`

Specifies the handle to the connection on which to create the clock.

`ClockCreate`

Specifies clock create parameters. This currently consists of a flag that must be set to zero.

`ClockHandle`

Specifies the new clock handle.


## Return Value

The <b>KsCreateClock</b> function returns STATUS_SUCCESS if successful, or it returns an error on clock creation failure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |