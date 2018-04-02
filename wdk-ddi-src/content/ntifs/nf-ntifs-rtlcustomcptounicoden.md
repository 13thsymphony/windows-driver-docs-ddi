---
UID: NF:ntifs.RtlCustomCPToUnicodeN
title: RtlCustomCPToUnicodeN function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\rtlcustomcptounicoden.htm
old-project: ifsk
ms.assetid: 8f29aca1-9d38-4c28-976f-64549767b303
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlCustomCPToUnicodeN, RtlCustomCPToUnicodeN function [Installable File System Drivers], ifsk.rtlcustomcptounicoden, ntifs/RtlCustomCPToUnicodeN, rtlref_9b39575d-4ba4-49fa-9281-2858d3e2631d.xml
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
-	RtlCustomCPToUnicodeN
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlCustomCPToUnicodeN function
The <b>RtlCustomCPToUnicodeN</b> routine is reserved for system use. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff553113">RtlMultiByteToUnicodeN</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553157">RtlOemToUnicodeN</a>.

## Syntax

```
NTSYSAPI NTSTATUS RtlCustomCPToUnicodeN(
  PCPTABLEINFO CustomCP,
  PWCH         UnicodeString,
  ULONG        MaxBytesInUnicodeString,
  PULONG       BytesInUnicodeString,
  PCH          CustomCPString,
  ULONG        BytesInCustomCPString
);
```

## Parameters

`CustomCP`

TBD

`UnicodeString`

TBD

`MaxBytesInUnicodeString`

TBD

`BytesInUnicodeString`

TBD

`CustomCPString`

TBD

`BytesInCustomCPString`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |