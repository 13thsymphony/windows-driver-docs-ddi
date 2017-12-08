---
UID: NF.wdm.ZwOpenKeyEx
title: ZwOpenKeyEx function
author: windows-driver-content
description: The ZwOpenKeyEx routine opens an existing registry key.
old-location: kernel\zwopenkeyex.htm
old-project: kernel
ms.assetid: 05057ae7-0f91-4f5a-8c72-652ec04ee3ab
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ZwOpenKeyEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwOpenKeyEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# ZwOpenKeyEx function



## -description
The <b>ZwOpenKeyEx</b> routine opens an existing registry key. 


## -syntax

````
NTSTATUS ZwOpenKeyEx(
  _Out_ PHANDLE            KeyHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes,
  _In_  ULONG              OpenOptions
);
````


## -parameters

### -param KeyHandle [out]

A pointer to a HANDLE variable into which the routine writes the handle to the key.

### -param DesiredAccess [in]

Specifies the type of access to the key that the caller requests. This parameter is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value. For more information, see the description of the <i>DesiredAccess</i> parameter of the <a href="kernel.zwcreatekey">ZwCreateKey</a> routine.

### -param ObjectAttributes [in]

A pointer to the object attributes of the key being opened. This parameter points to an <a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a> structure that must have been previously initialized by the <a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a> routine. The caller must specify the name of the registry key as the <i>ObjectName</i> parameter in the call to <b>InitializeObjectAttributes</b>. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 

### -param OpenOptions [in]

Specifies the options to apply when opening the key. Set this parameter to zero or to the bitwise OR of one or more of the following REG_OPTION_<i>XXX</i> flag bits:
<table>
<tr>
<th><i>OpenOptions</i> flag</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_OPTION_OPEN_LINK
</td>
<td>
The key is a symbolic link. This flag is not used by device and intermediate drivers.
</td>
</tr>
<tr>
<td>
REG_OPTION_BACKUP_RESTORE
</td>
<td>
The key should be opened with special privileges that allow backup and restore operations. This flag is not used by device and intermediate drivers.
</td>
</tr>
</table>
 

## -returns
<b>ZwOpenKeyEx</b> returns STATUS_SUCCESS if the call succeeds in opening the key. Possible error return values include the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>The <i>OpenOptions</i> parameter specifies invalid options. 
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>The registry path in the object attributes is invalid. 
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The registry key name in the object attributes was not found. 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The named registry key is a symbolic link, but the REG_OPTION_OPEN_LINK flag bit is not set in <i>OpenOptions</i>. 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller did not have the required access rights to open a handle for the named registry key.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A memory allocation operation failed. 

 

## -remarks
This routine supplies a handle with which the caller can access a registry key. If the specified key does not exist, the routine returns an error status value and does not supply a key handle.

The <a href="kernel.zwopenkey">ZwOpenKey</a> routine is similar to <b>ZwOpenKeyEx</b> but does not accept an <i>OpenOptions</i> parameter. The <i>OpenOptions</i> parameter of <b>ZwOpenKeyEx</b> enables the caller to open a key that is a symbolic link, or to open a key for backup and restore operations. A call to <b>ZwOpenKeyEx</b> with <i>OpenOptions</i> = 0 is equivalent to a call to <b>ZwOpenKey</b>.

After the handle pointed to by <i>KeyHandle</i> is no longer in use, the driver must call <a href="kernel.zwclose">ZwClose</a> to close it.

<b>ZwOpenKeyEx</b> ignores the security information in the structure that the <i>ObjectAttributes</i> parameter points to.

If the kernel-mode caller is not running in a system thread context, it must ensure that any handles it creates are kernel handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

For more information about working with registry keys in kernel mode, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7 and later versions of Windows. 
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
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
<dt>
<a href="kernel.zwopenkey">ZwOpenKey</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenKeyEx routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
