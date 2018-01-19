---
UID : NF:storport.StorPortInterlockedFlushSList
title : StorPortInterlockedFlushSList function
author : windows-driver-content
description : Removes all items from a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system.
old-location : storage\storportinterlockedflushslist.htm
old-project : storage
ms.assetid : C686ABA7-BC44-45CE-A35B-63E76961A032
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortInterlockedFlushSList
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : Available in starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : StorPortInterlockedFlushSList
req.alt-loc : storport.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortInterlockedFlushSList function
Removes all items from a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system

## Syntax

````
ULONG StorPortInterlockedFlushSList(
  _In_    PVOID               HwDeviceExtension,
  _Inout_ PSTOR_SLIST_HEADER  SListHead,
  _Out_   PSTOR_SLIST_ENTRY * Result
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`SListHead`

A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.

`Result`

A pointer to a list entry pointer. The value returned is a pointer to  the items removed from the list. If the list is empty, then <b>NULL</b> is returned in value pointed to by <i>Result</i>.


## Return Value

<b>StorPortInterlockedFlushSList</b> returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The list items were removed successfully or the list is already empty.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>A pointer in <i>SListHead</i> or <i>Result</i> is <b>NULL</b>.

## Remarks

The <b>StorPortInterlockedFlushSList</b> will also return <b>STATUS_SUCCESS</b> when no entries are in the list. The pointer value referenced by <i>Result</i> must be evaluated for <b>NULL</b> to verify that no entries were returned.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\storport\nf-storport-storportinitializeslisthead.md">StorPortInitializeSListHead</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportinterlockedpopentryslist.md">StorPortInterlockedPopEntrySList</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportinterlockedpushentryslist.md">StorPortInterlockedPushEntrySList</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportquerydepthslist.md">StorPortQueryDepthSList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInterlockedFlushSList routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>