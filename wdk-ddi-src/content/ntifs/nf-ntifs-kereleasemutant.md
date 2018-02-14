---
UID: NF:ntifs.KeReleaseMutant
title: KeReleaseMutant function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\kereleasemutant.htm
old-project: ifsk
ms.assetid: f5dc0f1b-3287-410d-97be-6d4f65466e65
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: keref_3bfd3822-4bbe-4d79-844e-afc6511d1bbb.xml, KeReleaseMutant function [Installable File System Drivers], ifsk.kereleasemutant, KeReleaseMutant, ntifs/KeReleaseMutant
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
-	KeReleaseMutant
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# KeReleaseMutant function
The <b>KeReleaseMutant</b> routine is reserved for system use. See <a href="..\wdm\nf-wdm-kereleasemutex.md">KeReleaseMutex</a>.

## Syntax

````
  KeReleaseMutant(
    
);
````

## Parameters

`Mutant`

TBD

`Increment`

TBD

`Abandoned`

TBD

`Wait`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |