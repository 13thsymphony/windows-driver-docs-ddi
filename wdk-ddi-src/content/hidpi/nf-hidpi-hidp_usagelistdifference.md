---
UID: NF:hidpi.HidP_UsageListDifference
title: HidP_UsageListDifference function
author: windows-driver-content
description: The HidP_UsageListDifference routine returns the differences between two arrays of HID usages.
old-location: hid\hidp_usagelistdifference.htm
old-project: hid
ms.assetid: 332ef453-6f9d-4cdd-a8c7-766158e540d8
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidP_UsageListDifference routine [Human Input Devices], HidP_UsageListDifference, hid.hidp_usagelistdifference, hidpi/HidP_UsageListDifference, hidfunc_91cbddd2-90f6-4784-9f1d-6d9bf8be35d3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hidparse.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hidparse.lib
-	Hidparse.dll
apiname:
-	HidP_UsageListDifference
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---


# HidP_UsageListDifference function
The <b>HidP_UsageListDifference</b> routine returns the differences between two arrays of <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">HID usages</a>.

## Syntax

````
NTSTATUS __stdcall HidP_UsageListDifference(
  _In_  PUSAGE PreviousUsageList,
  _In_  PUSAGE CurrentUsageList,
  _Out_ PUSAGE BreakUsageList,
  _Out_ PUSAGE MakeUsageList,
  _In_  ULONG  UsageListLength
);
````

## Parameters

`PreviousUsageList`

Pointer to a list of usages that the routine compares with the list of usages in <i>CurrentUsageList</i>.

`CurrentUsageList`

Pointer to a list of usages that the routine compares with the list of usages in <i>PreviousUsageList</i>.

`BreakUsageList`

Pointer to a caller-allocated buffer that, on return, contains a list of the usages that are in <i>PreviousUsageList</i>, but not in <i>CurrentUsageList</i>.

`MakeUsageList`

Pointer to a caller-allocated buffer that, on return, contains a list of the usages that are in <i>CurrentUsageList</i>, but not in <i>PreviousUsageList</i>.

`UsageListLength`

Specifies the length, in array elements, of the buffers provided at <i>CurrentUsageList </i>and <i>PreviousUsageList</i>.


## Return Value

<b>HidP_UsageListDifference</b> returns HIDP_STATUS_SUCCESS.

## Remarks

A user-mode application or kernel-mode driver can use this routine to compare two usage lists, for example, to determine the change in button state between two usage lists returned by two <a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a> calls.

If the input usage lists have different lengths, an application or driver should set <i>UsageListLength</i> to the length of the larger list.

The routine interprets a zero usage in an input usage list as a delimiter that ends the list. Any usages after a zero in a list are not processed. Unused usages in an output list are set to zero.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows. Available in Windows 2000 and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | hidpi.h (include Hidpi.h) |
| **Library** | Hidparse.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539824">HidP_UsageAndPageListDifference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_UsageListDifference routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>