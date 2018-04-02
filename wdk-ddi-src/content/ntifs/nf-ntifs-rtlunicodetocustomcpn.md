---
UID: NF:ntifs.RtlUnicodeToCustomCPN
title: RtlUnicodeToCustomCPN function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\rtlunicodetocustomcpn.htm
old-project: ifsk
ms.assetid: db4335c1-b6c9-4afd-b30f-95b736be696b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlUnicodeToCustomCPN, RtlUnicodeToCustomCPN function [Installable File System Drivers], ifsk.rtlunicodetocustomcpn, ntifs/RtlUnicodeToCustomCPN, rtlref_0c9942bd-a950-4d59-8fc7-58c41cfe78d4.xml
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
-	RtlUnicodeToCustomCPN
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlUnicodeToCustomCPN function
The <b>RtlUnicodeToCustomCPN</b> routine is reserved for system use. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff553261">RtlUnicodeToMultiByteN</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553272">RtlUnicodeToOemN</a>.

## Syntax

```
NTSYSAPI NTSTATUS RtlUnicodeToCustomCPN(
  PCPTABLEINFO CustomCP,
  PCH          CustomCPString,
  ULONG        MaxBytesInCustomCPString,
  PULONG       BytesInCustomCPString,
  PWCH         UnicodeString,
  ULONG        BytesInUnicodeString
);
```

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