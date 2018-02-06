---
UID: NS:wdm._REG_LOAD_KEY_INFORMATION
title: "_REG_LOAD_KEY_INFORMATION"
author: windows-driver-content
description: The REG_LOAD_KEY_INFORMATION structure contains information about a registry hive that is being loaded.
old-location: kernel\reg_load_key_information.htm
old-project: kernel
ms.assetid: 4012667b-d287-4846-8860-0cca977f9792
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PREG_LOAD_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], kstruct_d_31dae695-0a6f-4309-9c39-25c2df4a5b23.xml, REG_LOAD_KEY_INFORMATION, kernel.reg_load_key_information, PREG_LOAD_KEY_INFORMATION, wdm/PREG_LOAD_KEY_INFORMATION, *PREG_LOAD_KEY_INFORMATION, REG_LOAD_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_LOAD_KEY_INFORMATION, wdm/REG_LOAD_KEY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	REG_LOAD_KEY_INFORMATION
product: Windows
targetos: Windows
req.typenames: REG_LOAD_KEY_INFORMATION, *PREG_LOAD_KEY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_LOAD_KEY_INFORMATION structure
The <b>REG_LOAD_KEY_INFORMATION</b> structure contains information about a registry hive that is being loaded.

## Syntax
````
typedef struct _REG_LOAD_KEY_INFORMATION {
  PVOID           Object;
  PUNICODE_STRING KeyName;
  PUNICODE_STRING SourceFile;
  ULONG           Flags;
  PVOID           TrustClassObject;
  PVOID           UserEvent;
  ACCESS_MASK     DesiredAccess;
  PHANDLE         RootHandle;
  PVOID           CallContext;
  PVOID           ObjectContext;
  PVOID           Reserved;
} REG_LOAD_KEY_INFORMATION, *PREG_LOAD_KEY_INFORMATION;
````

## Members


`CallContext`

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply.

`DesiredAccess`

The access mask that was specified by the thread that is trying to load the registry key. For more information about this access mask, see the description of the <i>DesiredAccess</i> parameter of the <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> routine.

`Flags`

Reserved for system use.

`KeyName`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the root key.

`Object`

A pointer to the registry key object for the root key of the hive that is about to be loaded.

`ObjectContext`

A pointer to driver-defined context information that the driver has associated with a registry object by calling the <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a> routine.

`Reserved`

Reserved for system use.

`RootHandle`

An optional pointer to a location that receives the handle to the root of the hive that is being loaded. This member can be non-<b>NULL</b> if an application hive is  being loaded. In all other cases, this member should be <b>NULL</b>.

`SourceFile`

A pointer to a <b>UNICODE_STRING</b> structure that contains the path name of a file that contains the registry hive information that is being loaded.

`TrustClassObject`

Reserved for system use.

`UserEvent`

A pointer to an event object that is signaled when the hive is unloaded.

## Remarks
The operating system passes the <b>REG_LOAD_KEY_INFORMATION</b> structure to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a user-mode thread calls <a href="https://msdn.microsoft.com/536395aa-03ba-430d-a66d-fcabdc9dfe22">RegLoadKey</a> to load a registry hive.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>

<a href="https://msdn.microsoft.com/536395aa-03ba-430d-a66d-fcabdc9dfe22">RegLoadKey</a>

<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_LOAD_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>