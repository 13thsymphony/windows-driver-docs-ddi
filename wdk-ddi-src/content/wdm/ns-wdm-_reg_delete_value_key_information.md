---
UID : NS:wdm._REG_DELETE_VALUE_KEY_INFORMATION
title : "_REG_DELETE_VALUE_KEY_INFORMATION"
author : windows-driver-content
description : The REG_DELETE_VALUE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key's value is being deleted.
old-location : kernel\reg_delete_value_key_information.htm
old-project : kernel
ms.assetid : 7976ad9a-b40c-44b1-bc28-0bcb3b721e92
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kstruct_d_a95a729a-53de-4acc-a935-c2f60d7f9f18.xml, _REG_DELETE_VALUE_KEY_INFORMATION, PREG_DELETE_VALUE_KEY_INFORMATION, *PREG_DELETE_VALUE_KEY_INFORMATION, REG_DELETE_VALUE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], kernel.reg_delete_value_key_information, wdm/PREG_DELETE_VALUE_KEY_INFORMATION, REG_DELETE_VALUE_KEY_INFORMATION, wdm/REG_DELETE_VALUE_KEY_INFORMATION, PREG_DELETE_VALUE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available on Microsoft Windows XP and later versions of the Windows operating system.
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
req.typenames : REG_DELETE_VALUE_KEY_INFORMATION, *PREG_DELETE_VALUE_KEY_INFORMATION
req.product : Windows 10 or later.
---

# _REG_DELETE_VALUE_KEY_INFORMATION structure
The <b>REG_DELETE_VALUE_KEY_INFORMATION</b> structure contains information that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can use when a registry key's value is being deleted.

## Syntax
````
typedef struct _REG_DELETE_VALUE_KEY_INFORMATION {
  PVOID           Object;
  PUNICODE_STRING ValueName;
  PVOID           CallContext;
  PVOID           ObjectContext;
  PVOID           Reserved;
} REG_DELETE_VALUE_KEY_INFORMATION, *PREG_DELETE_VALUE_KEY_INFORMATION;
````

## Members


`CallContext`

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

`Object`

A pointer to the registry key object for the key whose value entry is about to be deleted.

`ObjectContext`

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

`Reserved`

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

`ValueName`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the value entry that is about to be deleted.

## Remarks
The system passes this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to delete a value entry—for example, when a user-mode thread calls <b>RegDeleteValue</b> or when a driver calls <a href="..\wdm\nf-wdm-zwdeletevaluekey.md">ZwDeleteValueKey</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP and later versions of the Windows operating system. Available on Microsoft Windows XP and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\nf-wdm-zwdeletevaluekey.md">ZwDeleteValueKey</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_DELETE_VALUE_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>