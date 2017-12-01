---
UID: NF.wdm.MmIsDriverVerifyingByAddress
title: MmIsDriverVerifyingByAddress
author: windows-driver-content
description: The MmIsDriverVerifyingByAddress routine checks whether the kernel-mode driver that is identified by the specified image address is being verified or calls a driver that is being verified by Driver Verifier.
old-location: kernel\mmisdriververifyingbyaddress.htm
old-project: kernel
ms.assetid: ccc20b5b-0f16-422d-8900-03b57f08b1bc
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: MmIsDriverVerifyingByAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmIsDriverVerifyingByAddress
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# MmIsDriverVerifyingByAddress function



## -description
<p>The <b>MmIsDriverVerifyingByAddress</b> routine checks whether the kernel-mode  driver that is identified by the specified image address is being verified or calls a driver that is being verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>.</p>


## -syntax

````
LOGICAL MmIsDriverVerifyingByAddress(
  _In_ PVOID AddressWithinSection
);
````


## -parameters
<dl>

### -param <i>AddressWithinSection</i> [in]

<dd>
<p>A pointer to the virtual address within the driver image. <b>MmIsDriverVerifyingByAddress</b> uses this address to determine which driver to check.</p>
</dd>
</dl>

## -returns
<p><b>MmIsDriverVerifyingByAddress</b> returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, this routine returns <b>FALSE</b>.</p>

## -remarks
<p>A kernel-mode driver can call this routine to determine whether it or another driver is being monitored by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="https://msdn.microsoft.com/7cdf5277-7187-4e90-b22a-6f828f06e2fb">Verifier Command Line</a> or <a href="https://msdn.microsoft.com/37a7d348-8b55-44f7-86d6-6b195704b9fd">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="NULL">Selecting Drivers to be Verified</a>.</p>

<p>A similar routine, <a href="..\wdm\nf-wdm-mmisdriververifying.md">MmIsDriverVerifying</a>, indicates whether a driver identified by a <a href="https://msdn.microsoft.com/497ee2dc-671d-408e-b228-16dc24532375">driver object</a> is being verified or calls a driver that is being verified.</p>

<p>Another related routine, <a href="..\wdm\nf-wdm-mmisdriversuspectforverifier.md">MmIsDriverSuspectForVerifier</a>, indicates whether a driver represented by a driver object is in the list of drivers that are selected to be verified.</p>

<p>For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifyingByAddress(Aobj)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(Badr)</code> returns <b>TRUE</b>, where <code>Aobj</code> is a pointer to the driver object for A and <code>Badr</code> is an address in driver B. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(Aobj)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifyingByAddress(Badr)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifyingByAddress(Cadr)</code> and <code>MmIsDriverSuspectForVerifier(Cobj)</code> both return <b>FALSE</b>.</p>

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
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
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
<p>&lt;=APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-mmisdriversuspectforverifier.md">MmIsDriverSuspectForVerifier</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmisdriververifying.md">MmIsDriverVerifying</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmIsDriverVerifyingByAddress routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
