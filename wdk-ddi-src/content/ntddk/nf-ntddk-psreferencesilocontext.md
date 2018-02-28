---
UID: NF:ntddk.PsReferenceSiloContext
title: PsReferenceSiloContext function
author: windows-driver-content
description: This routine increments the reference count on the object.
old-location: kernel\psreferencesilocontext.htm
old-project: kernel
ms.assetid: 04867D53-DB36-482A-93BF-C91D13998B3F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PsReferenceSiloContext, PsReferenceSiloContext routine [Kernel-Mode Driver Architecture], kernel.psreferencesilocontext, ntddk/PsReferenceSiloContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
req.irql: "_IRQL_requires_max_(DISPATCH_LEVEL)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsReferenceSiloContext
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsReferenceSiloContext function
This routine increments the reference count on the object.

## Syntax

````
void PsReferenceSiloContext(
  _In_ PVOID SiloContext
);
````

## Parameters

`SiloContext`

A pointer to the object created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>.


## Return Value

This routine does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "_IRQL_requires_max_(DISPATCH_LEVEL)" |

## See Also

<a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsReferenceSiloContext routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>