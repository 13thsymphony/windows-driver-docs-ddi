---
UID: NS:ntddk._WHEA_XPF_PROCINFO_VALIDBITS
title: "_WHEA_XPF_PROCINFO_VALIDBITS"
author: windows-driver-content
description: The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a WHEA_XPF_PROCINFO structure contain valid data.
old-location: whea\whea_xpf_procinfo_validbits.htm
old-project: whea
ms.assetid: ca0eef79-d990-4a82-b2d6-a51e3790cfc2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ntddk/WHEA_XPF_PROCINFO_VALIDBITS, ntddk/PWHEA_XPF_PROCINFO_VALIDBITS, PWHEA_XPF_PROCINFO_VALIDBITS, whea.whea_xpf_procinfo_validbits, whearef_6ebbdab8-0590-4479-a8ab-ea9bacf69399.xml, WHEA_XPF_PROCINFO_VALIDBITS, *PWHEA_XPF_PROCINFO_VALIDBITS, _WHEA_XPF_PROCINFO_VALIDBITS, WHEA_XPF_PROCINFO_VALIDBITS union [WHEA Drivers and Applications], PWHEA_XPF_PROCINFO_VALIDBITS union pointer [WHEA Drivers and Applications]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_XPF_PROCINFO_VALIDBITS
product: Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCINFO_VALIDBITS, *PWHEA_XPF_PROCINFO_VALIDBITS
---

# _WHEA_XPF_PROCINFO_VALIDBITS structure
The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structure contain valid data.

## Syntax
````
typedef union _WHEA_XPF_PROCINFO_VALIDBITS {
  struct {
    ULONGLONG CheckInfo  :1;
    ULONGLONG TargetId  :1;
    ULONGLONG RequesterId  :1;
    ULONGLONG ResponderId  :1;
    ULONGLONG InstructionPointer  :1;
    ULONGLONG Reserved  :59;
  };
  ULONGLONG ValidBits;
} WHEA_XPF_PROCINFO_VALIDBITS, *PWHEA_XPF_PROCINFO_VALIDBITS;
````

## Members


`DUMMYSTRUCTNAME`



`ValidBits`

A ULONGLONG representation of the contents of the WHEA_XPF_PROCINFO_VALIDBITS union.

## Remarks
A WHEA_XPF_PROCINFO_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCINFO_VALIDBITS union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>