---
UID : NF:ntifs.IoPageRead
title : IoPageRead function
author : windows-driver-content
description : Reserved for system use.
old-location : ifsk\iopageread.htm
old-project : ifsk
ms.assetid : d1cbd6ee-6625-47bd-bf3e-356b28ff17a5
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IoPageRead function [Installable File System Drivers], IoPageRead, ioref_2c5776f2-eef8-49e5-ade1-3ed0edcd6102.xml, ifsk.iopageread, ntifs/IoPageRead
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


# IoPageRead function
The <b>IoPageRead</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-cccopyread.md">CcCopyRead</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>.

## Syntax

````
  IoPageRead(
    
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
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |