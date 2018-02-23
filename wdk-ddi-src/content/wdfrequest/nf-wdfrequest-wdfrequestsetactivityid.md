---
UID: NF:wdfrequest.WdfRequestSetActivityId
title: WdfRequestSetActivityId function
author: windows-driver-content
description: The WdfRequestSetActivityId method associates an activity identifier with an I/O request.
old-location: wdf\wdfrequestsetactivityid.htm
old-project: wdf
ms.assetid: 05FE0F91-781F-4B8B-87D1-E06BC315856C
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfRequestSetActivityId method, wdf.wdfrequestsetactivityid, wdfrequest/WdfRequestSetActivityId, WdfRequestSetActivityId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WUDFx02000.dll
apiname:
-	WdfRequestSetActivityId
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestSetActivityId function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestSetActivityId</b> method associates an activity identifier with an I/O request.

## Syntax

````
void WdfRequestSetActivityId(
  _In_ WDFREQUEST Request,
  _In_ LPGUID     ActivityId
);
````

## Parameters

`Request`

A handle to a framework request object.

`ActivityId`

A pointer to the activity identifier GUID to store in the I/O request.


## Return Value

This method does not return a value.

## Remarks

Calling <b>WdfRequestSetActivityId</b> does not set an association with any previously present activity identifier. When the driver calls <b>WdfRequestSetActivityId</b>, any existing activity identifier is overwritten.

To set an association, retrieve the existing identifier by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveactivityid.md">WdfRequestRetrieveActivityId</a> and then associate the existing identifier with the new one by calling <a href="https://msdn.microsoft.com/798cf3ba-e1cc-4eaf-a1d2-2313a64aab1a">EventWriteTransfer</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>.

For more information about activity identifiers, see <a href="https://msdn.microsoft.com/2B70953F-5192-4654-9506-6A84373D20B4">Using Activity Identifiers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | WUDFx02000.lib |
| **DLL** | WUDFx02000.dll; TBD |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveactivityid.md">WdfRequestRetrieveActivityId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestSetActivityId method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>