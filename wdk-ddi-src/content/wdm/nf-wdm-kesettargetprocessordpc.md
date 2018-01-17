---
UID: NF:wdm.KeSetTargetProcessorDpc
title: KeSetTargetProcessorDpc function
author: windows-driver-content
description: The KeSetTargetProcessorDpc routine specifies the processor that a DPC routine will be run on.
old-location: kernel\kesettargetprocessordpc.htm
old-project: kernel
ms.assetid: 9fd86250-a495-4628-a07b-f5c44df69c0e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeSetTargetProcessorDpc
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
req.alt-api: KeSetTargetProcessorDpc
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSetTargetProcessorDpc function



## -description
The <b>KeSetTargetProcessorDpc</b> routine specifies the processor that a DPC routine will be run on.



## -syntax

````
VOID KeSetTargetProcessorDpc(
  _Inout_ PRKDPC Dpc,
  _In_    CCHAR  Number
);
````


## -parameters

### -param Dpc [in, out]

Pointer to the caller's DPC object, which <a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a> already initialized.


### -param Number [in]

Specifies the zero-based number of the target processor on which the DPC should be queued and executed.


## -returns
None


## -remarks
On multiprocessor systems, each processor has its own DPC queue. The <b>KeSetTargetProcessorDpc</b> routine specifies which processor's queue the system should use when the driver calls <a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a> or <a href="..\wdm\nf-wdm-iorequestdpc.md">IoRequestDpc</a> to queue a DPC to be run later.

Starting with Windows Vista, you can also use <b>KeSetTargetProcessorDpc</b> to specify the target processor for <a href="https://msdn.microsoft.com/library/windows/hardware/ff564621">threaded DPCs</a>.

A call to <b>KeSetTargetProcessorDpcEx</b> that occurs after a DPC object has been queued has no effect on the selection of a processor for the DPC routine to run on. To control the selection of the target processor, a <b>KeSetTargetProcessorDpc</b> call must occur before the call to <b>KeInsertQueueDpc</b> or <b>IoRequestDpc</b> that queues the DPC object.

For more information about DPC queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558754">Organization of DPC Queues</a>.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="..\wdm\nf-wdm-kesettargetprocessordpcex.md">KeSetTargetProcessorDpcEx</a> routine, which specifies a processor group, instead of <b>KeSetTargetProcessorDpc</b>, which does not. However, the implementation of <b>KeSetTargetProcessorDpc</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, if <i>Number</i> is less than the number of active logical processors in group 0, <b>KeSetTargetProcessorDpc</b> sets the target for the DPC to the processor in group 0 that is specified by <i>Number</i>. Otherwise, the DPC target does not change.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iorequestdpc.md">IoRequestDpc</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-kegetcurrentprocessornumber.md">KeGetCurrentProcessorNumber</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesetimportancedpc.md">KeSetImportanceDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesettargetprocessordpcex.md">KeSetTargetProcessorDpcEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetTargetProcessorDpc routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

