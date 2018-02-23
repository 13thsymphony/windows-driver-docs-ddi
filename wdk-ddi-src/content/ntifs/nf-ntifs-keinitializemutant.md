---
UID: NF:ntifs.KeInitializeMutant
title: KeInitializeMutant function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\keinitializemutant.htm
old-project: ifsk
ms.assetid: 75c31158-5d9c-465a-bb62-392b85fd8791
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeInitializeMutant, ifsk.keinitializemutant, KeInitializeMutant function [Installable File System Drivers], ntifs/KeInitializeMutant, keref_b0f59cc4-6d50-45bc-928c-3c2288ba0f14.xml
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
-	KeInitializeMutant
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# KeInitializeMutant function
The <b>KeInitializeMutant</b> routine is reserved for system use. See <a href="..\wdm\nf-wdm-keinitializemutex.md">KeInitializeMutex</a>.

## Syntax

````
  KeInitializeMutant(
    
);
````

## Parameters

`Mutant`

TBD

`InitialOwner`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |