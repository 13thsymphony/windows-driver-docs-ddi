---
UID: NF.wdm.KeRegisterBugCheckReasonCallback
title: KeRegisterBugCheckReasonCallback function
author: windows-driver-content
description: The KeRegisterBugCheckReasonCallback routine registers a BugCheckDumpIoCallback, BugCheckSecondaryDumpDataCallback, or BugCheckAddPagesCallback routine, which executes when the operating system issues a bug check.
old-location: kernel\keregisterbugcheckreasoncallback.htm
old-project: kernel
ms.assetid: 01528aa0-c580-4527-a64d-83f4ed39a471
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: KeRegisterBugCheckReasonCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP Service Pack 1 (SP1), Windows Server 2003, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeRegisterBugCheckReasonCallback
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
req.irql: Any level
req.product: Windows 10 or later.
---

# KeRegisterBugCheckReasonCallback function



## -description
The <b>KeRegisterBugCheckReasonCallback</b> routine registers a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>, or <a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a> routine, which executes when the operating system issues a bug check.



## -syntax

````
BOOLEAN KeRegisterBugCheckReasonCallback(
  _Out_ PKBUGCHECK_REASON_CALLBACK_RECORD  CallbackRecord,
  _In_  PKBUGCHECK_REASON_CALLBACK_ROUTINE CallbackRoutine,
  _In_  KBUGCHECK_CALLBACK_REASON          Reason,
  _In_  PUCHAR                             Component
);
````


## -parameters

### -param CallbackRecord [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a> structure that was initialized by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a> routine. 


### -param CallbackRoutine [in]

A pointer to the callback routine to register. This parameter points to one of the following types of driver-implemented routine: 

<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>


</dd>
<dd>

<a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a>


</dd>
</dl>

### -param Reason [in]

Specifies the type of callback routine that <i>CallbackRoutine</i> points to. Set <i>Reason</i> to one of the <a href="kernel.kbugcheck_callback_reason">KBUGCHECK_CALLBACK_REASON</a> enumeration values in the following table.

<table>
<tr>
<th>Value</th>
<th>Callback routine</th>
</tr>
<tr>
<td>
<b>KbCallbackDumpIo</b>

</td>
<td>
<i>BugCheckDumpIoCallback</i>

</td>
</tr>
<tr>
<td>
<b>KbCallbackSecondaryDumpData</b>

</td>
<td>
<i>BugCheckSecondaryDumpDataCallback</i>

</td>
</tr>
<tr>
<td>
<b>KbCallbackAddPages</b>

</td>
<td>
<i>BugCheckAddPagesCallback</i>

</td>
</tr>
</table>
 


### -param Component [in]

A pointer to a null-terminated ANSI string that identifies the caller. For example, you can select a string that describes the device driver, or that contains the device name. You can use the <a href="http://go.microsoft.com/fwlink/p/?linkid=165502">!bugdump</a> debugger extension to display the crash dump data that is associated with this string.


## -returns
<b>KeRegisterBugCheckReasonCallback</b> returns <b>TRUE</b> if the callback routine is successfully registered; otherwise, it returns <b>FALSE</b>.


## -remarks
Drivers can use <b>KeRegisterBugCheckReasonCallback</b> to register routines that execute during a system bug check.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a> routines are called each time data is written to the crash dump file. Drivers for devices that monitor the system state can register a <i>BugCheckDumpIoCallback</i> routine to copy the crash dump data to the monitoring device.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> routines are called to poll drivers for any device-specific information that should be added to the secondary data area of a crash dump file.


<a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a> routines are called to enable drivers to add pages of driver-specific data to the primary data area of a crash dump file. <i>BugCheckAddPagesCallback</i> routines are supported in Windows Server 2008 and later versions of Windows.

Drivers can use the <a href="kernel.kederegisterbugcheckreasoncallback">KeDeregisterBugCheckReasonCallback</a> routine to remove the <i>BugCheckXxxCallback</i> registration. Any driver that can be unloaded must remove the registrations of all of its callbacks in its <a href="kernel.unload">Unload</a> routine.

To display secondary dump data, you can use the <a href="http://go.microsoft.com/fwlink/p/?linkid=165501">.enumtag</a> command or the <a href="http://go.microsoft.com/fwlink/p/?linkid=165500">IDebugDataSpaces3::ReadTagged</a> method in a debugger extension. Another option is to debug the bug check callback routine itself. For more information about debuggers and debugger extensions, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.


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
Available in Windows XP Service Pack 1 (SP1), Windows Server 2003, and later versions of Windows.

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
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>
</dt>
<dt>
<a href="kernel.kbugcheck_callback_reason">KBUGCHECK_CALLBACK_REASON</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a>
</dt>
<dt>
<a href="kernel.kederegisterbugcheckreasoncallback">KeDeregisterBugCheckReasonCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a>
</dt>
<dt>
<a href="kernel.keregisterbugcheckcallback">KeRegisterBugCheckCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRegisterBugCheckReasonCallback routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

