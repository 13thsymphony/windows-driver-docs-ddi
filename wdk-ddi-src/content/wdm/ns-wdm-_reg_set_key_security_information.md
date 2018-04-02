---
UID: NS:wdm._REG_SET_KEY_SECURITY_INFORMATION
title: "_REG_SET_KEY_SECURITY_INFORMATION"
author: windows-driver-content
description: The REG_SET_KEY_SECURITY_INFORMATION structure specifies security information for a registry key object.
old-location: kernel\reg_set_key_security_information.htm
old-project: kernel
ms.assetid: 196bad19-85a6-41a0-ac61-b70594a19f0f
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PREG_SET_KEY_SECURITY_INFORMATION, PREG_SET_KEY_SECURITY_INFORMATION, PREG_SET_KEY_SECURITY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_SET_KEY_SECURITY_INFORMATION, REG_SET_KEY_SECURITY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_SET_KEY_SECURITY_INFORMATION, kernel.reg_set_key_security_information, kstruct_d_2154cf21-9f72-488b-ad13-687ada458991.xml, wdm/PREG_SET_KEY_SECURITY_INFORMATION, wdm/REG_SET_KEY_SECURITY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
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
-	wdm.h
api_name:
-	REG_SET_KEY_SECURITY_INFORMATION
product: Windows
targetos: Windows
req.typenames: REG_SET_KEY_SECURITY_INFORMATION, *PREG_SET_KEY_SECURITY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_SET_KEY_SECURITY_INFORMATION structure
The <b>REG_SET_KEY_SECURITY_INFORMATION</b> structure specifies security information for a registry key object.

## Syntax
```
typedef struct _REG_SET_KEY_SECURITY_INFORMATION {
  PVOID                 Object;
  PSECURITY_INFORMATION SecurityInformation;
  PSECURITY_DESCRIPTOR  SecurityDescriptor;
  PVOID                 CallContext;
  PVOID                 ObjectContext;
  PVOID                 Reserved;
} REG_SET_KEY_SECURITY_INFORMATION, *PREG_SET_KEY_SECURITY_INFORMATION;
```

## Members


`Object`

A pointer to the registry key object for the key whose security information is being set.

`SecurityInformation`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>-typed variable that identifies the type of security information that is being set.

`SecurityDescriptor`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> structure that contains security information for the key object.

`CallContext`

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

`ObjectContext`

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

`Reserved`

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## Remarks
The system passes the <b>REG_SET_KEY_SECURITY_INFORMATION</b> structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to set a key's security information—for example, when a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567106">ZwSetSecurityObject</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Windows Vista and later versions of the Windows operating system. Available on Windows Vista and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567106">ZwSetSecurityObject</a>