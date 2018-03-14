---
UID: NF:wudfwdm.InitializeListHead
title: InitializeListHead function
author: windows-driver-content
description: The InitializeListHead routine initializes a LIST_ENTRY structure that represents the head of a doubly linked list.
old-location: kernel\initializelisthead.htm
old-project: kernel
ms.assetid: 123434fd-4e83-4042-834b-1eb4cf13dd10
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: InitializeListHead, InitializeListHead routine [Kernel-Mode Driver Architecture], k109_2e5e02a0-26d3-4c8a-b712-ee3d515b8a23.xml, kernel.initializelisthead, wdm/InitializeListHead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	InitializeListHead
product: Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---


# InitializeListHead function
The <b>InitializeListHead</b> routine initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the head of a doubly linked list.

## Syntax

````
VOID InitializeListHead(
  _Out_ PLIST_ENTRY ListHead
);
````

## Parameters

`ListHead`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that serves as the list header.


## Return Value

None

## Remarks

The <b>InitializeListHead</b> routine sets the <b>Flink</b> and <b>Blink</b> members of <i>ListHead</i> to point to <i>ListHead</i>.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InitializeListHead</b> can be running at any IRQL. If <b>InitializeListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL the storage for <i>ListHead</i> must be resident.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h) |
| **IRQL** | Any level (see Remarks section) |

## See Also

<a href="..\wudfwdm\nf-wudfwdm-islistempty.md">IsListEmpty</a>



<a href="..\wdm\nf-wdm-exinterlockedinsertheadlist.md">ExInterlockedInsertHeadList</a>



<a href="..\wudfwdm\nf-wudfwdm-removeentrylist.md">RemoveEntryList</a>



<a href="..\wudfwdm\nf-wudfwdm-pushentrylist.md">PushEntryList</a>



<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wdm\nf-wdm-exinterlockedpushentrylist.md">ExInterlockedPushEntryList</a>



<a href="..\wudfwdm\nf-wudfwdm-insertheadlist.md">InsertHeadList</a>



<a href="..\wudfwdm\nf-wudfwdm-popentrylist.md">PopEntryList</a>



<a href="..\wudfwdm\nf-wudfwdm-removetaillist.md">RemoveTailList</a>



<a href="..\wudfwdm\nf-wudfwdm-removeheadlist.md">RemoveHeadList</a>



<a href="..\wdm\nf-wdm-exinterlockedpopentrylist.md">ExInterlockedPopEntryList</a>



<a href="..\wdm\nf-wdm-exinterlockedinserttaillist.md">ExInterlockedInsertTailList</a>



<a href="..\wdm\nf-wdm-exinterlockedremoveheadlist.md">ExInterlockedRemoveHeadList</a>



<a href="..\wudfwdm\nf-wudfwdm-inserttaillist.md">InsertTailList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InitializeListHead routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>