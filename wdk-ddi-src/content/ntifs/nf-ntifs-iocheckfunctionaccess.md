---
UID: NF:ntifs.IoCheckFunctionAccess
title: IoCheckFunctionAccess function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iocheckfunctionaccess.htm
old-project: ifsk
ms.assetid: 828a5197-eb2d-46d1-9853-0f8b4f288820
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/IoCheckFunctionAccess, ioref_e6c92504-238b-4163-8078-35aee716744e.xml, ifsk.iocheckfunctionaccess, IoCheckFunctionAccess, IoCheckFunctionAccess function [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	IoCheckFunctionAccess
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoCheckFunctionAccess function
The <b>IoCheckFunctionAccess</b> routine is reserved for system use. See <a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>.

## Syntax

````
  IoCheckFunctionAccess(
    
);
````

## Parameters

`GrantedAccess`

TBD

`MajorFunction`

TBD

`MinorFunction`

TBD

`IoControlCode`

TBD

`Arg1`

TBD

`Arg2`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |