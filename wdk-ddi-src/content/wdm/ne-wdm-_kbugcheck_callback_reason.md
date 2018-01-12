---
UID: NE:wdm._KBUGCHECK_CALLBACK_REASON
title: _KBUGCHECK_CALLBACK_REASON
author: windows-driver-content
description: The KBUGCHECK_CALLBACK_REASON enumeration type specifies the situations in which a bug-check callback executes.
old-location: kernel\kbugcheck_callback_reason.htm
old-project: kernel
ms.assetid: 08246843-9b6e-4694-8475-acb02fbdd82b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _KBUGCHECK_CALLBACK_REASON, KBUGCHECK_CALLBACK_REASON
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported on Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KBUGCHECK_CALLBACK_REASON
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
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: KBUGCHECK_CALLBACK_REASON
req.product: Windows 10 or later.
---

# _KBUGCHECK_CALLBACK_REASON enumeration



## -description
The <b>KBUGCHECK_CALLBACK_REASON</b> enumeration type specifies the situations in which a bug-check callback executes.



## -syntax

````
typedef enum _KBUGCHECK_CALLBACK_REASON { 
  KbCallbackInvalid            = 0,
  KbCallbackReserved1          = 1,
  KbCallbackSecondaryDumpData  = 2,
  KbCallbackDumpIo             = 3,
  KbCallbackAddPages           = 4
} KBUGCHECK_CALLBACK_REASON;
````


## -enum-fields

### -field KbCallbackInvalid

Reserved for system use. Do not use.


### -field KbCallbackReserved1

Reserved for system use. Do not use.


### -field KbCallbackSecondaryDumpData

Specifies that the callback is executed to provide data that the system appends to the secondary section of the crash dump file. For more information about this type of callback, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>.


### -field KbCallbackDumpIo

Specifies that the callback is executed each time a section of the dump file is written. For more information about this type of callback, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>.


### -field KbCallbackAddPages

Specifies that the callback is executed to provide one or more pages of data that the system adds to the primary section of the crash dump file. For more information about this type of callback, see <a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a>. This enumeration value is supported in Windows Server 2008 and later versions of Windows.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported on Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.

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
<a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_CALLBACK_REASON enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

