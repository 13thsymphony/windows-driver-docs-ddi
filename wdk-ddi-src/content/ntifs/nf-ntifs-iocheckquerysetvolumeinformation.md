---
UID: NF:ntifs.IoCheckQuerySetVolumeInformation
title: IoCheckQuerySetVolumeInformation function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\iocheckquerysetvolumeinformation.htm
old-project: ifsk
ms.assetid: b3bfd54d-9fd2-401a-b01d-32983f0a6021
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/IoCheckQuerySetVolumeInformation, IoCheckQuerySetVolumeInformation, ioref_67d57dbb-a3b0-4f78-9454-36c8b04e515c.xml, ifsk.iocheckquerysetvolumeinformation, IoCheckQuerySetVolumeInformation function [Installable File System Drivers]
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
-	IoCheckQuerySetVolumeInformation
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoCheckQuerySetVolumeInformation function
The <b>IoCheckQuerySetVolumeInformation</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>.

## Syntax

````
  IoCheckQuerySetVolumeInformation(
    
);
````

## Parameters

`FsInformationClass`

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