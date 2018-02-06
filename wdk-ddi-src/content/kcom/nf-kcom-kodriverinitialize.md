---
UID: NF:kcom.KoDriverInitialize
title: KoDriverInitialize function
author: windows-driver-content
description: The KoDriverInitialize function initializes a driver object to handle the kernel streaming interface.
old-location: stream\kodriverinitialize.htm
old-project: stream
ms.assetid: ed61d135-967d-4e7c-b437-09c9e0e6f3c2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kodriverinitialize, ksfunc_117817ed-5a64-48c4-8b90-1ca6435c75b6.xml, KoDriverInitialize function [Streaming Media Devices], KoDriverInitialize, kcom/KoDriverInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: kcom.h
req.include-header: Kcom.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KoDriverInitialize
product: Windows
targetos: Windows
req.typenames: "*PCONNECT_DATA, CONNECT_DATA"
---


# KoDriverInitialize function
<i>This function is intended for internal use only.</i>

The <b>KoDriverInitialize</b> function initializes a driver object to handle the kernel streaming interface.

## Syntax

````
NTSTATUS KoDriverInitialize(
  _In_ PDRIVER_OBJECT        DriverObject,
  _In_ PUNICODE_STRING       RegistryPathName,
  _In_ KoCreateObjectHandler CreateObjectHandler
);
````

## Parameters

`DriverObject`

Pointer to a driver object to initialize that handles the kernel streaming interface.

`RegistryPathName`

Pointer to the registry path that is associated with the driver object.

`CreateObjectHandler`

Pointer to a function used to create new objects.


## Return Value

Returns STATUS_SUCCESS if successful. Otherwise, it returns a memory allocation error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | kcom.h (include Kcom.h) |
| **Library** | Ks.lib |