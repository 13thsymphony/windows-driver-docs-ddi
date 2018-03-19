---
UID: NF:storport.StorPortReadRegisterUlong64
title: StorPortReadRegisterUlong64 macro
author: windows-driver-content
description: The StorPortReadRegisterUlong64 routine reads a 64-bit value from a specified 64-bit register address.
old-location: storage\storportreadregisterulong64.htm
old-project: storage
ms.assetid: 73A9E645-0B71-429F-9033-032BB83E60E4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReadRegisterUlong64, StorPortReadRegisterUlong64 routine [Storage Devices], storage.storportreadregisterulong64, storport/StorPortReadRegisterUlong64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortReadRegisterUlong64
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortReadRegisterUlong64 function
The <b>StorPortReadRegisterUlong64</b> routine reads a 64-bit value from a specified 64-bit register address.

## Syntax

````
 VOID StorPortReadRegisterUlong64(
  _In_ PULONG64  Register
);
````

## Parameters

`h`

TBD

`r`

TBD


## Return Value

None

## Remarks

The <b>StorPortReadRegisterUlong64</b> routine is only available on the 64-bit version of Windows.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |

## See Also

<a href="..\storport\nf-storport-storportwriteregisterulong64.md">StorPortWriteRegisterUlong64</a>