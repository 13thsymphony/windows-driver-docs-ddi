---
UID: NF:ntifs.IoQueryVolumeInformation
title: IoQueryVolumeInformation function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\ioqueryvolumeinformation.htm
old-project: ifsk
ms.assetid: f8226351-4a40-4c71-9ab4-4609ae7e0470
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.ioqueryvolumeinformation, IoQueryVolumeInformation, IoQueryVolumeInformation function [Installable File System Drivers], ioref_c048e59e-2f1e-4327-9f7f-b18e9a8e5724.xml, ntifs/IoQueryVolumeInformation
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
-	IoQueryVolumeInformation
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoQueryVolumeInformation function
The <b>IoQueryVolumeInformation</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>.

## Syntax

````
  IoQueryVolumeInformation(
    
);
````

## Parameters

`FileObject`

TBD

`FsInformationClass`

TBD

`Length`

TBD

`FsInformation`

TBD

`ReturnedLength`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |