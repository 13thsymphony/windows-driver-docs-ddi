---
UID: NF.ntddk.ZwPowerInformation
title: ZwPowerInformation
author: windows-driver-content
description: The ZwPowerInformation routine sets or retrieves system power information.
old-location: kernel\zwpowerinformation.htm
old-project: kernel
ms.assetid: BA1D5AD2-E3E5-42CB-8E77-627B23078F80
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ZwPowerInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwPowerInformation,NtPowerInformation
req.alt-loc: Ntoskrnl.lib
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.lib
req.irql: PASSIVE_LEVEL
req.iface: 
---

# ZwPowerInformation function



## -description
<p>The <b>ZwPowerInformation</b> routine sets or retrieves system power information.</p>


## -syntax

````
NTSTATUS ZwPowerInformation(
  _In_      POWER_INFORMATION_LEVEL InformationLevel,
  _In_opt_  PVOID                   InputBuffer,
  _In_      ULONG                   InputBufferLength,
  _Out_opt_ PVOID                   OutputBuffer,
  _In_      ULONG                   OutputBufferLength
);
````


## -parameters
<dl>

### -param InformationLevel [in]

<dd>
<p>Specifies the requested information level, which indicates the specific power information to be set or retrieved. Currently, the only supported <i>POWER_INFORMATION_LEVEL</i> value is <b>PlatformInformation</b>.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PlatformInformation"></a><a id="platforminformation"></a><a id="PLATFORMINFORMATION"></a><dl>

### -param PlatformInformation

</dl>
</td>
<td width="60%">
<p>Information represents the currently supported power capabilities of the system. Information may change as drivers are installed. For example, the installation of legacy device drivers that do not support power management might modify the capabilities of the system.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param InputBuffer [in, optional]

<dd>
<p>Pointer to a caller-allocated input buffer. This parameter must be <b>NULL</b>, otherwise <b>ERROR_INVALID_PARAMETER</b> is returned. </p>
</dd>

### -param InputBufferLength [in]

<dd>
<p>Size, in bytes, of the buffer at <i>InputBuffer</i>. The parameter must be set to zero.</p>
</dd>

### -param OutputBuffer [out, optional]

<dd>
<p>A pointer to an output buffer. The data type of this buffer depends on the information level requested in the <i>InformationLevel</i> parameter. For the <b>PlatformInformation</b> level, the only currently supported value, the <i>OutputBuffer </i> parameter is required and should be of the <a href="..\wdm\ns-wdm--power-platform-information.md">POWER_PLATFORM_INFORMATION</a> type.</p>
</dd>

### -param OutputBufferLength [in]

<dd>
<p>Size, in bytes, of the output buffer. Depending on the information level requested, the buffer may be variably sized. <i>PlatformInformation</i>, the only currently supported value, requires a buffer that is the size of a <a href="..\wdm\ns-wdm--power-platform-information.md">POWER_PLATFORM_INFORMATION</a> structure.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if the call is successful. If the call fails, possible error codes include the following:</p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The output buffer is of insufficient size to contain the data being returned.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The <b>PlatformInformation</b> information level, which is the only currently supported value, requires no input buffer and must contain an output buffer. The caller either supplied an input buffer or no output buffer.</p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>The caller had insufficient access rights to perform the requested action.</p>

<p> </p>

## -remarks
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn957451">NtPowerInformation</a> and <b>ZwPowerInformation</b> are two versions of the same Windows Native System Services routine.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

<p>This example illustrates a valid function call.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
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
<a href="..\wdm\ns-wdm--power-platform-information.md">POWER_PLATFORM_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwPowerInformation routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
