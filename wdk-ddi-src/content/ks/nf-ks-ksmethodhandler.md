---
UID: NF:ks.KsMethodHandler
title: KsMethodHandler function
author: windows-driver-content
description: The KsMethodHandler function handles methods requested through IOCTL_KS_METHOD. It works with all method identifiers defined by the sets. The function can only be called at PASSIVE_LEVEL.
old-location: stream\ksmethodhandler.htm
old-project: stream
ms.assetid: 730b5fae-3536-44ed-8f92-e4563a137be9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsMethodHandler, KsMethodHandler function [Streaming Media Devices], ks/KsMethodHandler, ksfunc_1f1959ed-e370-4ebb-9932-435c448a944b.xml, stream.ksmethodhandler
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsMethodHandler
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsMethodHandler function
The <b>KsMethodHandler</b> function handles methods requested through IOCTL_KS_METHOD. It works with all method identifiers defined by the sets. The function can only be called at PASSIVE_LEVEL.

## Syntax

```
KSDDKAPI NTSTATUS KsMethodHandler(
  PIRP               Irp,
  ULONG              MethodSetsCount,
  const KSMETHOD_SET *MethodSet
);
```

## Parameters

`Irp`

Specifies the IRP with the method request being handled.

`MethodSetsCount`

Indicates the number of method set structures being passed.

`MethodSet`

Specifies the pointer to the list of method set information.


## Return Value

The <b>KsMethodHandler</b> function returns STATUS_SUCCESS if successful, or an error specific to the method being handled if unsuccessful. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero because of an internal error, unless the element is set by a method handler. The function does not set the IO_STATUS_BLOCK.Status field nor complete the IRP.

## Remarks

The owner of a method set can perform prefiltering or postfiltering of the method handling using the <b>KsMethodHandler</b> and <b>KsFastMethodHandler </b>functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561940">KsFastMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>