---
UID: NS.WDM._REG_LOAD_KEY_INFORMATION
title: _REG_LOAD_KEY_INFORMATION
author: windows-driver-content
description: The REG_LOAD_KEY_INFORMATION structure contains information about a registry hive that is being loaded.
old-location: kernel\reg_load_key_information.htm
old-project: kernel
ms.assetid: 4012667b-d287-4846-8860-0cca977f9792
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _REG_LOAD_KEY_INFORMATION, REG_LOAD_KEY_INFORMATION, PREG_LOAD_KEY_INFORMATION, *PREG_LOAD_KEY_INFORMATION
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
req.alt-api: REG_LOAD_KEY_INFORMATION
req.alt-loc: Wdm.h
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
req.product: Windows 10 or later.
---

# _REG_LOAD_KEY_INFORMATION structure



## -description
The <b>REG_LOAD_KEY_INFORMATION</b> structure contains information about a registry hive that is being loaded.



## -syntax

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


## -struct-fields

### -field Object

A pointer to the registry key object for the root key of the hive that is about to be loaded.


### -field KeyName

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains the name of the root key.


### -field SourceFile

A pointer to a <b>UNICODE_STRING</b> structure that contains the path name of a file that contains the registry hive information that is being loaded.


### -field Flags

Reserved for system use.


### -field TrustClassObject

Reserved for system use.


### -field UserEvent

A pointer to an event object that is signaled when the hive is unloaded.


### -field DesiredAccess

The access mask that was specified by the thread that is trying to load the registry key. For more information about this access mask, see the description of the <i>DesiredAccess</i> parameter of the <a href="kernel.zwcreatekey">ZwCreateKey</a> routine.


### -field RootHandle

An optional pointer to a location that receives the handle to the root of the hive that is being loaded. This member can be non-<b>NULL</b> if an application hive is  being loaded. In all other cases, this member should be <b>NULL</b>.


### -field CallContext

Optional driver-defined context information that the driver's <a href="kernel.registrycallback">RegistryCallback</a> routine can supply.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling the <a href="kernel.cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a> routine.


### -field Reserved

Reserved for system use.


## -remarks
The operating system passes the <b>REG_LOAD_KEY_INFORMATION</b> structure to a <a href="kernel.registrycallback">RegistryCallback</a> routine every time a user-mode thread calls <a href="base.regloadkey">RegLoadKey</a> to load a registry hive.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>
</dt>
<dt>
<a href="kernel.registrycallback">RegistryCallback</a>
</dt>
<dt>
<a href="base.regloadkey">RegLoadKey</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="kernel.zwcreatekey">ZwCreateKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_LOAD_KEY_INFORMATION structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

