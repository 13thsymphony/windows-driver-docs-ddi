---
UID: NF.wdm.ZwEnumerateKey
title: ZwEnumerateKey function
author: windows-driver-content
description: The ZwEnumerateKey routine returns information about a subkey of an open registry key.
old-location: kernel\zwenumeratekey.htm
old-project: kernel
ms.assetid: 77ccd451-40c7-4f64-af2b-480e44e7f672
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ZwEnumerateKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwEnumerateKey,NtEnumerateKey
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
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

# ZwEnumerateKey function



## -description
The <b>ZwEnumerateKey</b> routine returns information about a subkey of an open registry key.



## -syntax

````
NTSTATUS ZwEnumerateKey(
  _In_      HANDLE                KeyHandle,
  _In_      ULONG                 Index,
  _In_      KEY_INFORMATION_CLASS KeyInformationClass,
  _Out_opt_ PVOID                 KeyInformation,
  _In_      ULONG                 Length,
  _Out_     PULONG                ResultLength
);
````


## -parameters

### -param KeyHandle [in]

Handle to the registry key that contains the subkeys to be enumerated. The handle is created by a successful call to <a href="kernel.zwcreatekey">ZwCreateKey</a> or <a href="kernel.zwopenkey">ZwOpenKey</a>. 


### -param Index [in]

The index of the subkey that you want information for. If the key has <i>n</i> subkeys, the subkeys are numbered from 0 to <i>n</i>-1. 


### -param KeyInformationClass [in]

Specifies a <a href="kernel.key_information_class">KEY_INFORMATION_CLASS</a> enumeration value that determines the type of information to be received by the <i>KeyInformation</i> buffer. Set <i>KeyInformationClass</i> to one of the following values:

<ul>
<li><b>KeyBasicInformation</b></li>
<li><b>KeyFullInformation</b></li>
<li><b>KeyNodeInformation</b></li>
</ul>
If any value not in this list is specified, the routine returns error code STATUS_INVALID_PARAMETER.


### -param KeyInformation [out, optional]

Pointer to a caller-allocated buffer that receives the requested information. The <i>KeyInformationClass</i> parameter determines the type of information provided. 


### -param Length [in]

Specifies the size, in bytes, of the <i>KeyInformation</i> buffer. 


### -param ResultLength [out]

Pointer to a variable that receives the size, in bytes, of the registry-key information. If <b>ZwEnumerateKey</b> returns STATUS_SUCCESS, you can use the value of this variable to determine the amount of data returned. If the routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, you can use the value of this variable to determine the size of buffer required to hold the key information. 


## -returns
<b>ZwEnumerateKey</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. Possible error code values include:
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The buffer supplied is too small, and only partial data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer supplied is too small, and no data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>KeyInformationClass</i> parameter is not a valid KEY_INFORMATION_CLASS value.
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>The <i>Index</i> value is out of range for the registry key specified by <i>KeyHandle</i>. For example, if a key has <i>n</i> subkeys, then for any value greater than <i>n</i>-1 the routine returns STATUS_NO_MORE_ENTRIES. 

 


## -remarks
The handle must have been opened with KEY_ENUMERATE_SUB_KEYS access. This is accomplished by passing KEY_ENUMERATE_SUB_KEYS, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="kernel.zwcreatekey">ZwCreateKey</a> or <a href="kernel.zwopenkey">ZwOpenKey</a>.

The <i>Index</i> parameter is simply a way to select among subkeys of the key referred to by the <i>KeyHandle</i>. Two calls to <b>ZwEnumerateKey</b> with the same <i>Index</i> are not guaranteed to return the same result.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


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
Available starting with Windows 2000.

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
<a href="devtest.wdm_irqlzwpassive">IrqlZwPassive</a>, <a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.wdm_zwregistrycreate">ZwRegistryCreate</a>, <a href="devtest.wdm_zwregistryopen">ZwRegistryOpen</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_zwregistrycreate">ZwRegistryCreate(storport)</a>, <a href="devtest.storport_zwregistryopen">ZwRegistryOpen(storport)</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.key_basic_information">KEY_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_full_information">KEY_FULL_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_information_class">KEY_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.key_node_information">KEY_NODE_INFORMATION</a>
</dt>
<dt>
<a href="kernel.rtlcheckregistrykey">RtlCheckRegistryKey</a>
</dt>
<dt>
<a href="kernel.rtlcreateregistrykey">RtlCreateRegistryKey</a>
</dt>
<dt>
<a href="kernel.rtldeleteregistryvalue">RtlDeleteRegistryValue</a>
</dt>
<dt>
<a href="kernel.rtlqueryregistryvalues">RtlQueryRegistryValues</a>
</dt>
<dt>
<a href="kernel.rtlwriteregistryvalue">RtlWriteRegistryValue</a>
</dt>
<dt>
<a href="kernel.zwcreatekey">ZwCreateKey</a>
</dt>
<dt>
<a href="kernel.zwenumeratevaluekey">ZwEnumerateValueKey</a>
</dt>
<dt>
<a href="kernel.zwopenkey">ZwOpenKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwEnumerateKey routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

