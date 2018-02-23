---
UID: NF:ntifs.IoCheckQuerySetFileInformation
title: IoCheckQuerySetFileInformation function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iocheckquerysetfileinformation.htm
old-project: ifsk
ms.assetid: c68cbdb4-bdf8-4c18-8f96-7274021f9ac2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.iocheckquerysetfileinformation, ntifs/IoCheckQuerySetFileInformation, IoCheckQuerySetFileInformation function [Installable File System Drivers], IoCheckQuerySetFileInformation, ioref_22478455-1bd1-46cb-8ac2-05e4857c9524.xml
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
-	IoCheckQuerySetFileInformation
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoCheckQuerySetFileInformation function
The <b>IoCheckQuerySetFileInformation</b> routine is reserved for system use. See <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> and <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>.

## Syntax

````
  IoCheckQuerySetFileInformation(
    
);
````

## Parameters

`FileInformationClass`

TBD

`Length`

TBD

`SetOperation`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |