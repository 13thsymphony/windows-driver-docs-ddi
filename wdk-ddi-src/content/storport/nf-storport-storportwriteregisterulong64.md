---
UID : NF:storport.StorPortWriteRegisterUlong64
title : StorPortWriteRegisterUlong64 macro
author : windows-driver-content
description : This StorPortWriteRegisterUlong64 routine writes a ULONG64 value to the specified register address.
old-location : storage\storportwriteregisterulong64.htm
old-project : storage
ms.assetid : FFBC7A27-B980-49AF-9207-237E0F0292FA
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortWriteRegisterUlong64, storage.storportwriteregisterulong64, storport/StorPortWriteRegisterUlong64, StorPortWriteRegisterUlong64 routine [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : storport.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortWriteRegisterUlong64 function
This <b>StorPortWriteRegisterUlong64</b> routine writes a <b>ULONG64</b> value to the specified register address.

## Syntax

````
 VOID StorPortWriteRegisterUlong64(
  _In_ PULONG64  Register,
  _In_ ULONG64   Value
);
````

## Parameters

`h`

TBD

`r`

TBD

`v`

TBD


## Return Value

None

## Remarks

The <b>StorPortWriteRegisterUlong64</b> routine is only available on the 64-bit version of Windows.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\storport\nf-storport-storportreadregisterulong64.md">StorPortReadRegisterUlong64</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWriteRegisterUlong64 routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>