---
UID: NS:wdm._REG_REPLACE_KEY_INFORMATION
title: "_REG_REPLACE_KEY_INFORMATION"
author: windows-driver-content
description: The REG_REPLACE_KEY_INFORMATION structure describes the metadata that is about to be replaced for a key.
old-location: kernel\reg_replace_key_information.htm
old-project: kernel
ms.assetid: bbe60db6-85ae-480c-8852-80935a52697e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PREG_REPLACE_KEY_INFORMATION, PREG_REPLACE_KEY_INFORMATION, PREG_REPLACE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_REPLACE_KEY_INFORMATION, REG_REPLACE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_REPLACE_KEY_INFORMATION, kernel.reg_replace_key_information, kstruct_d_29e33c32-67fc-48e0-a976-9830278009bc.xml, wdm/PREG_REPLACE_KEY_INFORMATION, wdm/REG_REPLACE_KEY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista SP2 and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	REG_REPLACE_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_REPLACE_KEY_INFORMATION, *PREG_REPLACE_KEY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_REPLACE_KEY_INFORMATION structure
The <b>REG_REPLACE_KEY_INFORMATION</b> structure describes the metadata that is about to be replaced for a key.

## Syntax
```
typedef struct _REG_REPLACE_KEY_INFORMATION {
  PVOID           Object;
  PUNICODE_STRING OldFileName;
  PUNICODE_STRING NewFileName;
  PVOID           CallContext;
  PVOID           ObjectContext;
  PVOID           Reserved;
} REG_REPLACE_KEY_INFORMATION, *PREG_REPLACE_KEY_INFORMATION;
```

## Members


`Object`

A pointer to a registry key object for the key whose metadata is about to be replaced.

`OldFileName`

The name of the file that receives a backup copy of the registry information being replaced.

`NewFileName`

The name of the file with the registry information. This file is typically created by using the <b>RegSaveKey</b> function.

`CallContext`

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

`ObjectContext`

A pointer to driver-defined context information, which the driver has associated with a registry object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

`Reserved`

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## Remarks
The system passes this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to replace the metadata for a key.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Windows Vista SP2 and later versions of the Windows operating system. Available on Windows Vista SP2 and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>