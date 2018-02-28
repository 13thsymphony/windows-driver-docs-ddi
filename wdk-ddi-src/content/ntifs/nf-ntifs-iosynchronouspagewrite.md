---
UID: NF:ntifs.IoSynchronousPageWrite
title: IoSynchronousPageWrite function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iosynchronouspagewrite.htm
old-project: ifsk
ms.assetid: 3d66b517-91cd-44f7-8dfe-853468c49352
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoSynchronousPageWrite, IoSynchronousPageWrite function [Installable File System Drivers], ifsk.iosynchronouspagewrite, ioref_9ed81b03-18f6-4641-8f4e-b12c4afcfc5d.xml, ntifs/IoSynchronousPageWrite
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	IoSynchronousPageWrite
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoSynchronousPageWrite function
The <b>IoSynchronousPageWrite</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>, <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>, and <a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>.

## Syntax

````
  IoSynchronousPageWrite(
    
);
````

## Parameters

`FileObject`

TBD

`MemoryDescriptorList`

TBD

`StartingOffset`

TBD

`Event`

TBD

`IoStatusBlock`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |