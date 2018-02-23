---
UID: NS:sti._STI_DIAG
title: "_STI_DIAG"
author: windows-driver-content
description: The STI_DIAG structure is used as a parameter to the IStiDevice::Diagnostic and IStiUSD::Diagnostic methods.
old-location: image\sti_diag.htm
old-project: Image
ms.assetid: 07caa8b0-849c-4ad9-9adb-b1726edc9234
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: STI_DIAG, DIAG, STI_DIAG structure [Imaging Devices], sti/STI_DIAG, LPSTI_DIAG structure pointer [Imaging Devices], stifnc_793c0930-51bf-46b5-89c9-9ddaf91a1fee.xml, image.sti_diag, *LPSTI_DIAG, LPSTI_DIAG, _STI_DIAG, sti/LPSTI_DIAG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sti.h
req.include-header: Sti.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sti.h
apiname:
-	STI_DIAG
product: Windows
targetos: Windows
req.typenames: "*LPSTI_DIAG, STI_DIAG"
req.product: Windows 10 or later.
---

# _STI_DIAG structure
The STI_DIAG structure is used as a parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543814">IStiUSD::Diagnostic</a> methods.

## Syntax
````
typedef struct _STI_DIAG {
  DWORD          dwSize;
  DWORD          dwBasicDiagCode;
  DWORD          dwVendorDiagCode;
  DWORD          dwStatusMask;
  STI_ERROR_INFO sErrorInfo;
} STI_DIAG, *LPSTI_DIAG;
````

## Members


`dwBasicDiagCode`

Bit flag indicating the type of test to be performed. Currently this must be STI_DIAGCODE_HWPRESENCE<i>.</i>

`dwSize`

Caller-supplied size, in bytes, of the STI_DIAG structure.

`dwStatusMask`

Reserved for future use.

`dwVendorDiagCode`

Optional, vendor-defined diagnostic request code.

`sErrorInfo`

Structure of type <a href="..\sti\ns-sti-_error_infow.md">STI_ERROR_INFO</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sti.h (include Sti.h) |