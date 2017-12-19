---
UID: NS.WDM._REG_CREATE_KEY_INFORMATION
title: _REG_CREATE_KEY_INFORMATION
author: windows-driver-content
description: The REG_CREATE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key that is being created.
old-location: kernel\reg_create_key_information.htm
old-project: kernel
ms.assetid: 5609a2c4-71db-432a-8a39-e407130a6e4c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _REG_CREATE_KEY_INFORMATION, REG_CREATE_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION, PREG_OPEN_KEY_INFORMATION, *PREG_CREATE_KEY_INFORMATION, PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2003, but some structure members are available only in Windows Vista and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_CREATE_KEY_INFORMATION
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

# _REG_CREATE_KEY_INFORMATION structure



## -description
The <b>REG_CREATE_KEY_INFORMATION</b> structure contains information that a driver's <a href="kernel.registrycallback">RegistryCallback</a> routine can use when a registry key that is being created.



## -syntax

````
typedef struct _REG_CREATE_KEY_INFORMATION {
  PUNICODE_STRING CompleteName;
  PVOID           RootObject;
  PVOID           ObjectType;
  ULONG           CreateOptions;
  PUNICODE_STRING Class;
  PVOID           SecurityDescriptor;
  PVOID           SecurityQualityOfService;
  ACCESS_MASK     DesiredAccess;
  ACCESS_MASK     GrantedAccess;
  PULONG          Disposition;
  PVOID           *ResultObject;
  PVOID           CallContext;
  PVOID           RootObjectContext;
  PVOID           Transaction;
  PVOID           Reserved;
} REG_CREATE_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION, *PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION;
````


## -struct-fields

### -field CompleteName

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains the path of the new registry key. The path can be absolute or relative. If the path is absolute, this structure contains a fully qualified path that starts with the "\" character. For an absolute path, the <b>RootObject</b> member specifies the <b>\REGISTRY</b> key, which is the root directory of the registry tree. If the path is relative, the path starts with a character other than "\", and is relative to the key that is specified by the <i>RootObject</i> member.


### -field RootObject

Pointer to the registry key object that serves as the root for the path specified by the <i>CompleteName</i> member.


### -field ObjectType

The <b>ObjectType</b> member is reserved for internal use. Drivers must not access this member. This member is defined starting with Windows Vista.


### -field CreateOptions

A bitwise OR of flags. For more information about these flags, see the <i>CreateOptions</i> parameter of the <a href="kernel.zwcreatekey">ZwCreateKey</a> routine. This member is defined starting with Windows Vista.


### -field Class

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that identifies the key's object class. For more information about this member, see the <i>Class</i> parameter of the <a href="kernel.zwcreatekey">ZwCreateKey</a> routine. This member is defined starting with Windows Vista.


### -field SecurityDescriptor

A pointer to a <a href="ifsk.security_descriptor">SECURITY_DESCRIPTOR</a> structure that contains security information for the key object. This member is defined starting with Windows Vista.


### -field SecurityQualityOfService

A pointer to a <b>SECURITY_QUALITY_OF_SERVICE</b> structure, which is defined in Winnt.h. This member is defined starting with Windows Vista.


### -field DesiredAccess

The access mask that was specified by the thread that is attempting to create the registry key. This member is defined starting with Windows Vista.


### -field GrantedAccess

An access mask that indicates the access rights that have been granted to the thread that is attempting to create the registry key. For more information about this member, see Remarks. This member is defined starting with Windows Vista.


### -field Disposition

A value that indicates whether the registry key was created. For more information about this member, see the <i>Disposition</i> parameter of the <a href="kernel.zwcreatekey">ZwCreateKey</a> routine and the following Remarks section. This member is defined starting with Windows Vista.


### -field ResultObject

A pointer to a location that receives the address of the key object that represents the created registry key. For more information about this member, see Remarks. This member is defined starting with Windows Vista.


### -field CallContext

Optional driver-defined context information that the driver's <a href="kernel.registrycallback">RegistryCallback</a> routine can supply. This member is defined starting with Windows Vista.


### -field RootObjectContext

A pointer to a driver-defined context information that the driver has associated with the root of the path for the registry object by calling <a href="kernel.cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.


### -field Transaction

A pointer to a transaction object that the operation is attempted on. If this member is <b>NULL</b>, the operation is being performed in non-transactional context. This member is defined starting with Windows Vista.


### -field Reserved

Starting with Windows Vista, if this member is 1, then it is safe to cast this structure to type <a href="kernel.reg_create_key_information_v1">REG_CREATE_KEY_INFORMATION_V1</a>, which contains additional parameters.

In versions of Windows before Windows Vista, this member is always 0.


## -remarks
The configuration manager passes this structure to the <a href="kernel.registrycallback">RegistryCallback</a> routine every time a thread attempts to create a key—for example, when a user-mode thread calls <b>RegCreateKey</b> or <b>RegCreateKeyEx</b> or when a driver calls <a href="kernel.zwcreatekey">ZwCreateKey</a>.

If the driver's <i>RegistryCallback</i> routine returns STATUS_CALLBACK_BYPASS for a <b>RegNtPreCreateKeyEx</b> notification, the driver must supply the <b>GrantedAccess</b>, <b>Disposition</b>, and <b>ResultObject</b> values.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Server 2003, but some structure members are available only in Windows Vista and later versions.

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
<a href="kernel.reg_create_key_information_v1">REG_CREATE_KEY_INFORMATION_V1</a>
</dt>
<dt>
<a href="kernel.reg_post_operation_information">REG_POST_OPERATION_INFORMATION</a>
</dt>
<dt>
<a href="kernel.registrycallback">RegistryCallback</a>
</dt>
<dt>
<a href="ifsk.security_descriptor">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="kernel.zwcreatekey">ZwCreateKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_CREATE_KEY_INFORMATION structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

