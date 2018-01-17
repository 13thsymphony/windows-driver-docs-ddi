---
UID: NF:ntddk.KeQueryTickCount
title: KeQueryTickCount function
author: windows-driver-content
description: The KeQueryTickCount routine maintains a count of the interval timer interrupts that have occurred since the system was booted.
old-location: kernel\kequerytickcount.htm
old-project: kernel
ms.assetid: 7cd0ed27-a056-4ed9-8ff4-e917b31b0dd6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeQueryTickCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeQueryTickCount
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
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# KeQueryTickCount function



## -description
The <b>KeQueryTickCount</b> routine maintains a count of the interval timer interrupts that have occurred since the system was booted. 



## -syntax

````
VOID KeQueryTickCount(
  _Out_ PLARGE_INTEGER TickCount
);
````


## -parameters

### -param TickCount [out]

Pointer to the tick count value on return from <b>KeQueryTickCount</b>.


## -returns
None


## -remarks
The <i>TickCount</i> value increases by one at each interval timer interrupt while the system is running.

The preferred method of determining elapsed time is by using <i>TickCount</i> for relative timing and time stamps.

To determine the absolute elapsed time multiply the returned <i>TickCount</i> by the <a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a> return value using compiler support for 64-bit integer operations.

You should not make any assumptions about the length of a tick, because it might vary depending on hardware and other considerations. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryTickCount routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

