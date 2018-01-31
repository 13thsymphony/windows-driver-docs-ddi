---
UID : NF:ntifs.RtlAllocateAndInitializeSid
title : RtlAllocateAndInitializeSid function
author : windows-driver-content
description : Reserved for system use.
old-location : ifsk\rtlallocateandinitializesid.htm
old-project : ifsk
ms.assetid : c58f4448-06f5-4eda-a254-e453defd1d6c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.rtlallocateandinitializesid, RtlAllocateAndInitializeSid, ntifs/RtlAllocateAndInitializeSid, RtlAllocateAndInitializeSid function [Installable File System Drivers], rtlref_74879713-f57f-4d67-a779-995c150bc7ea.xml
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


# RtlAllocateAndInitializeSid function
The <b>RtlAllocateAndInitializeSid</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-rtlcopysid.md">RtlCopySid</a> and <a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>.

## Syntax

````
  RtlAllocateAndInitializeSid(
    
);
````

## Parameters

`IdentifierAuthority`

TBD

`SubAuthorityCount`

TBD

`SubAuthority0`

TBD

`SubAuthority1`

TBD

`SubAuthority2`

TBD

`SubAuthority3`

TBD

`SubAuthority4`

TBD

`SubAuthority5`

TBD

`SubAuthority6`

TBD

`SubAuthority7`

TBD

`Sid`

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