---
UID: NF:ntifs.IoGetBaseFileSystemDeviceObject
title: IoGetBaseFileSystemDeviceObject function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iogetbasefilesystemdeviceobject.htm
old-project: ifsk
ms.assetid: 12a326d8-8628-496d-96e7-8c680aeb1a03
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoGetBaseFileSystemDeviceObject, IoGetBaseFileSystemDeviceObject function [Installable File System Drivers], ifsk.iogetbasefilesystemdeviceobject, ioref_008b0d20-a816-4f24-9439-ffe97ac8dc04.xml, ntifs/IoGetBaseFileSystemDeviceObject
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
-	IoGetBaseFileSystemDeviceObject
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoGetBaseFileSystemDeviceObject function
The <b>IoGetBaseFileSystemDeviceObject</b> routine is reserved for system use. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff548365">IoGetDeviceAttachmentBaseRef</a>.

## Syntax

```
NTKERNELAPI PDEVICE_OBJECT IoGetBaseFileSystemDeviceObject(
  PFILE_OBJECT FileObject
);
```

## Parameters

`FileObject`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |