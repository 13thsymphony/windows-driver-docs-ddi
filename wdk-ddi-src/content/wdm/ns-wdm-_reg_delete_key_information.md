---
UID : NS:wdm._REG_DELETE_KEY_INFORMATION
title : "_REG_DELETE_KEY_INFORMATION"
author : windows-driver-content
description : The REG_DELETE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key is being deleted.
old-location : kernel\reg_delete_key_information.htm
old-project : kernel
ms.assetid : 6137ab93-7128-4e71-ba4f-604c7e025c91
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : REG_FLUSH_KEY_INFORMATION, _REG_DELETE_KEY_INFORMATION, *PREG_FLUSH_KEY_INFORMATION, wdm/REG_DELETE_KEY_INFORMATION, kstruct_d_9069d571-f056-490e-b263-7849fd26b041.xml, *PREG_DELETE_KEY_INFORMATION, kernel.reg_delete_key_information, wdm/PREG_DELETE_KEY_INFORMATION, REG_DELETE_KEY_INFORMATION, REG_DELETE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], PREG_DELETE_KEY_INFORMATION, PREG_DELETE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available for Microsoft Windows XP and later versions of the Windows operating system, but some structure members are available only for Windows Vista and later versions.
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
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : REG_FLUSH_KEY_INFORMATION, REG_DELETE_KEY_INFORMATION, *PREG_DELETE_KEY_INFORMATION, *PREG_FLUSH_KEY_INFORMATION
req.product : Windows 10 or later.
---

# _REG_DELETE_KEY_INFORMATION structure
The <b>REG_DELETE_KEY_INFORMATION</b> structure contains information that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can use when a registry key is being deleted.

## Syntax
````
typedef struct _REG_DELETE_KEY_INFORMATION {
  PVOID Object;
  PVOID CallContext;
  PVOID ObjectContext;
  PVOID Reserved;
} REG_DELETE_KEY_INFORMATION, *PREG_DELETE_KEY_INFORMATION;
````

## Members


`CallContext`

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

`Object`

A pointer to the registry key object for the key to be deleted.

`ObjectContext`

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

`Reserved`

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## Remarks
The system passes this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to delete a key—for example, when a user-mode thread calls <b>RegDeleteKey</b> or <b>RegDeleteKeyEx</b> or when a driver calls <a href="..\wdm\nf-wdm-zwdeletekey.md">ZwDeleteKey</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available for Microsoft Windows XP and later versions of the Windows operating system, but some structure members are available only for Windows Vista and later versions. Available for Microsoft Windows XP and later versions of the Windows operating system, but some structure members are available only for Windows Vista and later versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>

<a href="..\wdm\nf-wdm-zwdeletekey.md">ZwDeleteKey</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_DELETE_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>