---
UID: NF:ks.KsPersistDeviceProfile
title: KsPersistDeviceProfile function
author: windows-driver-content
description: The KsPersistDeviceProfile API commits the profile information to the persistent store.
old-location: stream\kspersistdeviceprofile.htm
old-project: stream
ms.assetid: 4EC3E99B-C73C-4EAC-9EBD-BB45ABFCE8EC
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kspersistdeviceprofile, ks/KsPersistDeviceProfile, KsPersistDeviceProfile function [Streaming Media Devices], KsPersistDeviceProfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ksmedia.h
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
-	ks.lib
-	ks.dll
apiname:
-	KsPersistDeviceProfile
product: Windows
targetos: Windows
req.typenames: 
---


# KsPersistDeviceProfile function
The <b>KsPersistDeviceProfile</b> API commits the profile information to the persistent store.

## Syntax

````
 __drv_maxIRQL(PASSIVE_LEVEL) KSDDKAPI NTSTATUS NTAPI KsPersistDeviceProfile(
  _In_ PKSFILTERFACTORY FilterFactory
);
````

## Parameters

`FilterFactory`

This is the <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> that was used to initialize the profile store in <a href="..\ks\nf-ks-ksinitializedeviceprofile.md">KsInitializeDeviceProfile</a>.


## Return Value

If <b>KsPersistDeviceProfile</b> is called without first initializing the profile store with <b>KsInitializeDeviceProfile</b> the call to <b>KsPersistDeviceProfile</b> will fail with <b>STATUS_INVALID_DEVICE_REQUEST</b>.
Furthermore, this API may also fail with <b>STATUS_INSUFFICIENT_RESOURCE</b> if the page pool is exhausted when profile information is being persisted.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ksmedia.h) |
| **Library** | Ks.lib |