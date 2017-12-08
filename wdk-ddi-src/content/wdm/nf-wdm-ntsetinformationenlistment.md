---
UID: NF.wdm.NtSetInformationEnlistment
title: NtSetInformationEnlistment
author: windows-driver-content
description: The ZwSetInformationEnlistment routine sets information for a specified enlistment object.
old-location: kernel\zwsetinformationenlistment.htm
old-project: kernel
ms.assetid: c87547b0-a16e-48b5-91ca-c414c5317ac6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NtSetInformationEnlistment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwSetInformationEnlistment,NtSetInformationEnlistment
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
req.iface: 
req.product: Windows 10 or later.
---

# NtSetInformationEnlistment function



## -description
<p>The <b>ZwSetInformationEnlistment</b> routine sets information for a specified <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.</p>


## -syntax

````
NTSTATUS ZwSetInformationEnlistment(
  _In_ HANDLE                       EnlistmentHandle,
  _In_ ENLISTMENT_INFORMATION_CLASS EnlistmentInformationClass,
  _In_ PVOID                        EnlistmentInformation,
  _In_ ULONG                        EnlistmentInformationLength
);
````


## -parameters
<dl>

### -param EnlistmentHandle [in]

<dd>
<p>A handle to an enlistment object that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a> or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_SET_INFORMATION access to the object.</p>
</dd>

### -param EnlistmentInformationClass [in]

<dd>
<p>A <a href="..\wdm\ne-wdm--enlistment-information-class.md">ENLISTMENT_INFORMATION_CLASS</a>-typed enumeration value that specifies the type of information to be set. This value must be <b>EnlistmentRecoveryInformation</b>.</p>
<p>The enumeration's <b>EnlistmentBasicInformation</b> and <b>EnlistmentFullInformation</b> values are not used with <b>ZwSetInformationEnlistment</b>. </p>
</dd>

### -param EnlistmentInformation [in]

<dd>
<p>A pointer to a caller-allocated buffer that contains caller-defined recovery information for the enlistment.</p>
</dd>

### -param EnlistmentInformationLength [in]

<dd>
<p>The length, in bytes, of the buffer that the <i>EnlistmentInformation</i> parameter points to.</p>
</dd>
</dl>

## -returns
<p><b>ZwSetInformationEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: </p><dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl><p>The specified handle is not a handle to an enlistment object.</p><dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><p>The object handle is invalid.</p><dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl><p>The <i>EnlistmentInformationClass</i> parameter's value is invalid.</p><dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl><p>The <i>EnlistmentInformationLength</i> parameter's value is invalid.</p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>The caller does not have appropriate access to the enlistment object.</p>

<p> </p>

<p>The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

## -remarks
<p>A resource manager can use the <b>ZwSetInformationEnlistment</b> routine to set recovery information for an enlistment. KTM writes the recovery information to the log stream, and the resource manager can call <a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a> to read this information from the log stream at any time.</p>

<p>Each subsequent call to <b>ZwSetInformationEnlistment</b> deletes the recovery information that the previous call specified before it stores the new recovery information.</p>

<p>For more information about how to use <b>ZwSetInformationEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565415">Using Log Streams with KTM</a>.</p>

<p><b>NtSetInformationEnlistment</b> and <b>ZwSetInformationEnlistment</b> are two versions of the same Windows Native System Services routine. </p>

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
<p>Available in Windows Vista and later operating system versions.</p>
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
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm--enlistment-information-class.md">ENLISTMENT_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetInformationEnlistment routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
