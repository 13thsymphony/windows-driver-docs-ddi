---
UID: NF:ks.KsAcquireResetValue
title: KsAcquireResetValue function
author: windows-driver-content
description: The KsAcquireResetValue function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP.
old-location: stream\ksacquireresetvalue.htm
old-project: stream
ms.assetid: 80a990e3-3637-4837-8800-42d5848e01cf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_fbfd5f64-6842-4559-9829-05797fda4fa2.xml, KsAcquireResetValue, stream.ksacquireresetvalue, KsAcquireResetValue function [Streaming Media Devices], ks/KsAcquireResetValue
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
-	KsAcquireResetValue
product: Windows
targetos: Windows
req.typenames: 
---


# KsAcquireResetValue function
The <b>KsAcquireResetValue </b>function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP.

## Syntax

````
NTSTATUS KsAcquireResetValue(
  _In_  PIRP    Irp,
  _Out_ KSRESET *ResetValue
);
````

## Parameters

`Irp`

Points to the IRP from which to retrieve the reset state.

`ResetValue`

Points to a caller-allocated buffer, that on successful completion contains the reset value (KSRESET_BEGIN, KSRESET_END) associated with the IRP.


## Return Value

The <b>KsAcquireResetValue </b>function returns STATUS_SUCCESS if the reset value was obtained.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |