---
UID : NF:ntifs.IoSetInformation
title : IoSetInformation function
author : windows-driver-content
description : Reserved for system use.
old-location : ifsk\iosetinformation.htm
old-project : ifsk
ms.assetid : 6eedef2d-9fa5-4001-9246-7445198c4386
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.iosetinformation, ioref_3c058acd-e360-4923-a9be-b17d3882727f.xml, IoSetInformation, IoSetInformation function [Installable File System Drivers], ntifs/IoSetInformation
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# IoSetInformation function
The <b>IoSetInformation</b> routine is reserved for system use. See <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>.

## Syntax

````
  IoSetInformation(
    
);
````

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
| **Library** | NtosKrnl.exe |