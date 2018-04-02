---
UID: NF:ntifs.IoSetInformation
title: IoSetInformation function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iosetinformation.htm
old-project: ifsk
ms.assetid: 6eedef2d-9fa5-4001-9246-7445198c4386
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoSetInformation, IoSetInformation function [Installable File System Drivers], ifsk.iosetinformation, ioref_3c058acd-e360-4923-a9be-b17d3882727f.xml, ntifs/IoSetInformation
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
req.lib: 
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
-	IoSetInformation
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoSetInformation function
The <b>IoSetInformation</b> routine is reserved for system use. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>.

## Syntax

```
NTKERNELAPI NTSTATUS IoSetInformation(
  PFILE_OBJECT           FileObject,
  FILE_INFORMATION_CLASS FileInformationClass,
  ULONG                  Length,
  PVOID                  FileInformation
);
```

## Parameters

`FileObject`

TBD

`FileInformationClass`

TBD

`Length`

TBD

`FileInformation`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |