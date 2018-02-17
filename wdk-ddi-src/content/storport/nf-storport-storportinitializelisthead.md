---
UID: NF:storport.StorPortInitializeListHead
title: StorPortInitializeListHead function
author: windows-driver-content
description: The StorPortInitializeListHead routine initializes a STOR_LIST_ENTRY structure that represents the head of a doubly linked list.
old-location: storage\storportinitializelisthead.htm
old-project: storage
ms.assetid: E37C54C1-209F-4944-940B-2247E86C8130
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortInitializeListHead, storage.storportinitializelisthead, StorPortInitializeListHead, StorPortInitializeListHead routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortInitializeListHead
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortInitializeListHead function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>StorPortInitializeListHead</b> routine initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the head of a doubly linked list.

## Syntax

````
VOID StorPortInitializeListHead(
  _In_  PVOID            HwDeviceExtension,
  _Out_ PSTOR_LIST_ENTRY ListHead
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`ListHead`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the head of the list.


## Return Value

This routine does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wdm\nf-wdm-initializelisthead.md">InitializeListHead</a>



<a href="..\storport\nf-storport-storportinterlockedinsertheadlist.md">StorPortInterlockedInsertHeadList</a>



<a href="..\storport\nf-storport-storportinterlockedinserttaillist.md">StorPortInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt790430">StorPortInterlockedRemoveHeadList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializeListHead routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>