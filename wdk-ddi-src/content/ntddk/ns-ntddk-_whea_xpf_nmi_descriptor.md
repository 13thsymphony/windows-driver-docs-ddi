---
UID: NS:ntddk._WHEA_XPF_NMI_DESCRIPTOR
title: "_WHEA_XPF_NMI_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_XPF_NMI_DESCRIPTOR structure describes a nonmaskable interrupt (NMI) error source for an x86 or x64 processor.
old-location: whea\whea_xpf_nmi_descriptor.htm
old-project: whea
ms.assetid: 4ffacbd6-dcdf-48a2-bf1e-6923d825bb09
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_XPF_NMI_DESCRIPTOR, PWHEA_XPF_NMI_DESCRIPTOR, PWHEA_XPF_NMI_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_XPF_NMI_DESCRIPTOR, WHEA_XPF_NMI_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_XPF_NMI_DESCRIPTOR, ntddk/PWHEA_XPF_NMI_DESCRIPTOR, ntddk/WHEA_XPF_NMI_DESCRIPTOR, whea.whea_xpf_nmi_descriptor, whearef_47fae29e-d302-4028-961c-358ac647c0cc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_XPF_NMI_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WHEA_XPF_NMI_DESCRIPTOR, *PWHEA_XPF_NMI_DESCRIPTOR
---

# _WHEA_XPF_NMI_DESCRIPTOR structure
The WHEA_XPF_NMI_DESCRIPTOR structure describes a nonmaskable interrupt (NMI) error source for an x86 or x64 processor.

## Syntax
```
typedef struct _WHEA_XPF_NMI_DESCRIPTOR {
  USHORT  Type;
  BOOLEAN Enabled;
} WHEA_XPF_NMI_DESCRIPTOR, *PWHEA_XPF_NMI_DESCRIPTOR;
```

## Members


`Type`

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_XPFNMI.

`Enabled`

A Boolean value that indicates if the error source is enabled.

## Remarks
A WHEA_XPF_NMI_DESCRIPTOR structure is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>