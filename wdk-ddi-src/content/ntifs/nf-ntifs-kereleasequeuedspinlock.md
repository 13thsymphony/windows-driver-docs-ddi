---
UID: NF:ntifs.KeReleaseQueuedSpinLock
title: KeReleaseQueuedSpinLock function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\kereleasequeuedspinlock.htm
old-project: ifsk
ms.assetid: d10baf1a-149d-4499-89de-e151327218f7
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ntifs/KeReleaseQueuedSpinLock, keref_8815930f-e691-4759-ac40-3ebbe95e9116.xml, ifsk.kereleasequeuedspinlock, KeReleaseQueuedSpinLock function [Installable File System Drivers], KeReleaseQueuedSpinLock
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
-	KeReleaseQueuedSpinLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# KeReleaseQueuedSpinLock function
The <b>KeReleaseQueuedSpinLock</b> routine is reserved for system use.

## Syntax

````
  KeReleaseQueuedSpinLock(
    
);
````

## Parameters

`Number`

TBD

`OldIrql`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |