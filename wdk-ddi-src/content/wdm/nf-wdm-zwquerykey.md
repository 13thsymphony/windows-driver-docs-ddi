---
UID: NF.wdm.ZwQueryKey
title: ZwQueryKey
author: windows-driver-content
description: The ZwQueryKey routine provides information about the class of a registry key, and the number and sizes of its subkeys.
old-location: kernel\zwquerykey.htm
old-project: kernel
ms.assetid: 3b2d3a8b-a21f-4067-a1f0-9aa66c1973f5
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ZwQueryKey
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
req.alt-api: ZwQueryKey,NtQueryKey
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
req.iface: 
req.product: Windows 10 or later.
---

# ZwQueryKey function



## -description
<p>The <b>ZwQueryKey</b> routine provides information about the class of a registry key, and the number and sizes of its subkeys.</p>


## -syntax

````
NTSTATUS ZwQueryKey(
  _In_      HANDLE                KeyHandle,
  _In_      KEY_INFORMATION_CLASS KeyInformationClass,
  _Out_opt_ PVOID                 KeyInformation,
  _In_      ULONG                 Length,
  _Out_     PULONG                ResultLength
);
````


## -parameters
<dl>

### -param <i>KeyHandle</i> [in]

<dd>
<p>Handle to the registry key to obtain information about. This handle is created by a successful call to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>. </p>
</dd>

### -param <i>KeyInformationClass</i> [in]

<dd>
<p>Specifies a <a href="..\wdm\ne-wdm--key-information-class.md">KEY_INFORMATION_CLASS</a> value that determines the type of information returned in the <i>KeyInformation</i> buffer. </p>
</dd>

### -param <i>KeyInformation</i> [out, optional]

<dd>
<p>Pointer to a caller-allocated buffer that receives the requested information.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>Specifies the size, in bytes, of the <i>KeyInformation</i> buffer. </p>
</dd>

### -param <i>ResultLength</i> [out]

<dd>
<p>Pointer to a variable that receives the size, in bytes, of the requested key information. If <b>ZwQueryKey</b> returns STATUS_SUCCESS, the variable contains the amount of data returned. If <b>ZwQueryKey</b> returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, you can use the value of the variable to determine the required buffer size. </p>
</dd>
</dl>

## -returns
<p><b>ZwQueryKey</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:</p><dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl><p>The buffer supplied is too small, and only partial data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. </p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The buffer supplied is too small, and no data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. </p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The <i>KeyInformationClass</i> parameter is not a valid <a href="..\wdm\ne-wdm--key-information-class.md">KEY_INFORMATION_CLASS</a> value. </p>

<p> </p>

## -remarks
<p>The<i> KeyHandle</i> passed to <b>ZwQueryKey</b> must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>.</p>

<p><b>ZwQueryKey</b> can be used to obtain information that you can use to allocate buffers to hold registry data, such as the maximum size of a key's value entries or subkey names, or the number of subkeys. For example, you can call <b>ZwQueryKey</b>, use the returned information to allocate a buffer for a subkey, call <a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a> to get the name of the subkey, and pass that name to an <b>Rtl</b><b><i>Xxx</i></b><b>Registry</b> routine.</p>

<p>For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.wdm_irqlzwpassive">IrqlZwPassive</a>, <a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.wdm_zwregistrycreate">ZwRegistryCreate</a>, <a href="devtest.wdm_zwregistryopen">ZwRegistryOpen</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_zwregistrycreate">ZwRegistryCreate(storport)</a>, <a href="devtest.storport_zwregistryopen">ZwRegistryOpen(storport)</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--key-basic-information.md">KEY_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--key-cached-information.md">KEY_CACHED_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--key-full-information.md">KEY_FULL_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm--key-information-class.md">KEY_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--key-name-information.md">KEY_NAME_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--key-node-information.md">KEY_NODE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--key-virtualization-information.md">KEY_VIRTUALIZATION_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryKey routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
