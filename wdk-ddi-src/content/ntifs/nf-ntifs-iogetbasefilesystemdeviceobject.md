---
UID: NF:ntifs.IoGetBaseFileSystemDeviceObject
title: IoGetBaseFileSystemDeviceObject function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iogetbasefilesystemdeviceobject.htm
old-project: ifsk
ms.assetid: 12a326d8-8628-496d-96e7-8c680aeb1a03
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoGetBaseFileSystemDeviceObject, ifsk.iogetbasefilesystemdeviceobject, IoGetBaseFileSystemDeviceObject function [Installable File System Drivers], ntifs/IoGetBaseFileSystemDeviceObject, ioref_008b0d20-a816-4f24-9439-ffe97ac8dc04.xml
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
-	IoGetBaseFileSystemDeviceObject
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoGetBaseFileSystemDeviceObject function
The <b>IoGetBaseFileSystemDeviceObject</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-iogetdeviceattachmentbaseref.md">IoGetDeviceAttachmentBaseRef</a>.

## Syntax

````
  IoGetBaseFileSystemDeviceObject(
    
);
````

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
| **Library** | NtosKrnl.exe |