---
UID: NF:wdm.ExDeleteResourceLite
title: ExDeleteResourceLite function
author: windows-driver-content
description: The ExDeleteResourceLite routine deletes a given resource from the system's resource list.
old-location: kernel\exdeleteresourcelite.htm
old-project: kernel
ms.assetid: 83efb1eb-4c45-4bfc-84dd-88032e40076a
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExDeleteResourceLite, ExDeleteResourceLite routine [Kernel-Mode Driver Architecture], k102_92907ac3-1391-4ede-8ffa-71a211c7634e.xml, kernel.exdeleteresourcelite, wdm/ExDeleteResourceLite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte3, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExDeleteResourceLite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExDeleteResourceLite function
The <b>ExDeleteResourceLite</b> routine deletes a given resource from the system's resource list.

## Syntax

````
NTSTATUS ExDeleteResourceLite(
  _Inout_ PERESOURCE Resource
);
````

## Parameters

`Resource`

A pointer to the caller-supplied storage for the initialized resource variable to be deleted.


## Return Value

<b>ExDeleteResourceLite</b> returns STATUS_SUCCESS if the resource was deleted.

## Remarks

After calling <b>ExDeleteResourceLite</b>, the caller can free the memory it allocated for its resource.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | IrqlExApcLte3, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-exreinitializeresourcelite.md">ExReinitializeResourceLite</a>



<a href="..\wdm\nf-wdm-exinitializeresourcelite.md">ExInitializeResourceLite</a>



<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>