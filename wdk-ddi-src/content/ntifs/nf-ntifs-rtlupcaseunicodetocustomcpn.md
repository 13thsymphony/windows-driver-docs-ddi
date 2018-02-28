---
UID: NF:ntifs.RtlUpcaseUnicodeToCustomCPN
title: RtlUpcaseUnicodeToCustomCPN function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\rtlupcaseunicodetocustomcpn.htm
old-project: ifsk
ms.assetid: 906dd8c6-a7a7-4722-9ca6-78c437ab29e8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUpcaseUnicodeToCustomCPN, RtlUpcaseUnicodeToCustomCPN function [Installable File System Drivers], ifsk.rtlupcaseunicodetocustomcpn, ntifs/RtlUpcaseUnicodeToCustomCPN, rtlref_d60b8055-e672-4cc6-be0f-f9a23a202368.xml
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
-	RtlUpcaseUnicodeToCustomCPN
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlUpcaseUnicodeToCustomCPN function
The <b>RtlUpcaseUnicodeToCustomCPN</b> routine is reserved for system use. See <a href="..\ntifs\nf-ntifs-rtlupcaseunicodetomultibyten.md">RtlUpcaseUnicodeToMultiByteN</a> and <a href="..\ntifs\nf-ntifs-rtlupcaseunicodetooemn.md">RtlUpcaseUnicodeToOemN</a>.

## Syntax

````
  RtlUpcaseUnicodeToCustomCPN(
    
);
````

## Parameters

`CustomCP`

TBD

`CustomCPString`

TBD

`MaxBytesInCustomCPString`

TBD

`BytesInCustomCPString`

TBD

`UnicodeString`

TBD

`BytesInUnicodeString`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.exe |