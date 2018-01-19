---
UID : NF:wdm.KeRevertToUserGroupAffinityThread
title : KeRevertToUserGroupAffinityThread function
author : windows-driver-content
description : The KeRevertToUserGroupAffinityThread routine restores the group affinity of the calling thread to its original value at the time that the thread was created.
old-location : kernel\kereverttousergroupaffinitythread.htm
old-project : kernel
ms.assetid : 13a1a106-0c5c-4c0e-964d-27e549e1c699
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : KeRevertToUserGroupAffinityThread
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Ntddk.h, Wdm.h, Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KeRevertToUserGroupAffinityThread
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= DISPATCH_LEVEL (see Remarks section).
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# KeRevertToUserGroupAffinityThread function
The <b>KeRevertToUserGroupAffinityThread</b> routine restores the group affinity of the calling thread to its original value at the time that the thread was created.

## Syntax

````
VOID KeRevertToUserGroupAffinityThread(
  _In_ PGROUP_AFFINITY PreviousAffinity
);
````

## Parameters

`PreviousAffinity`

A pointer to the group affinity to restore. This parameter points to a <a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a> structure that contains a group number and an affinity mask. The affinity mask specifies the set of logical processors that the user thread can run on.


## Return Value

None

## Remarks

This routine changes the group number and group-relative affinity mask of the calling thread. The group number and affinity mask identify a set of processors on which the thread can run. If successful, the routine schedules the thread to run on a processor in this set.

The <i>PreviousAffinity</i> parameter points to a <b>GROUP_AFFINITY</b> structure that specifies the new group number (<b>Group</b> member) and affinity mask (<b>Mask</b> member) for the thread. If <i>PreviousAffinity</i>-&gt;<b>Mask</b> is nonzero, <b>KeRevertToUserGroupAffinityThread</b> sets the group number and affinity mask of the calling thread to the values in the structure. If <i>PreviousAffinity</i>-&gt;<b>Mask</b> is zero, the routine restores the group number and affinity mask to their original values at the time that the thread was initialized.

A process can have affinity for more than one group at a time. However, a thread can be assigned to only one group at any time, and that group is always in the affinity of the thread's process.

A thread can change the group to which it is assigned by calling the <a href="..\wdm\nf-wdm-kesetsystemgroupaffinitythread.md">KeSetSystemGroupAffinityThread</a> routine. Following one or more calls to <b>KeSetSystemGroupAffinityThread</b>, the thread can restore the original group affinity that it had when the thread was created by calling <b>KeRevertToUserGroupAffinityThread</b>.

After the thread is created, a call to <b>KeRevertToUserGroupAffinityThread</b> has no effect (that is, the group number and affinity mask of the thread remain unchanged) unless the thread first calls <b>KeSetSystemGroupAffinityThread</b>. Following a call to <b>KeRevertToUserGroupAffinityThread</b>, a second call to <b>KeRevertToUserGroupAffinityThread</b> has no effect unless the thread first calls <b>KeSetSystemGroupAffinityThread</b>.

The routine changes the group number and affinity mask to the values that are specified in *<i>PreviousAffinity</i> only if the following are true:

The group number is valid.

The affinity mask is valid (that is, only mask bits that correspond to logical processors in the group are set).

At least one of the processors that is specified in the affinity mask is active.

If any of these conditions is not met, the call to <b>KeRevertToUserGroupAffinityThread</b> has no effect.

A related routine, <a href="..\wdm\nf-wdm-kereverttouseraffinitythreadex.md">KeRevertToUserAffinityThreadEx</a>, changes the affinity mask of the calling thread, but this routine, unlike <b>KeRevertToUserGroupAffinityThread</b>, does not accept a group number as an input parameter. In Windows 7 and later versions of the Windows operating system, <b>KeRevertToUserAffinityThreadEx</b> assumes that the affinity mask refers to processors in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeRevertToUserAffinityThreadEx</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeRevertToUserGroupAffinityThread</b> instead of <b>KeRevertToUserAffinityThreadEx</b>.

If <b>KeRevertToUserGroupAffinityThread</b> is called at IRQL &lt;= APC_LEVEL and the call is successful, the new (reverted) group affinity takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new group affinity. If <b>KeRevertToUserGroupAffinityThread</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Ntddk.h, Wdm.h, Ntddk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL (see Remarks section). |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kereverttouseraffinitythreadex.md">KeRevertToUserAffinityThreadEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesetsystemgroupaffinitythread.md">KeSetSystemGroupAffinityThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRevertToUserGroupAffinityThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>