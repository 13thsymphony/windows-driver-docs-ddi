---
UID: NF:wdfrequest.WdfRequestSetActivityId
title: WdfRequestSetActivityId function
author: windows-driver-content
description: The WdfRequestSetActivityId method associates an activity identifier with an I/O request.
old-location: wdf\wdfrequestsetactivityid.htm
old-project: wdf
ms.assetid: 05FE0F91-781F-4B8B-87D1-E06BC315856C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfRequestSetActivityId, WdfRequestSetActivityId method, wdf.wdfrequestsetactivityid, wdfrequest/WdfRequestSetActivityId
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfRequestSetActivityId
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestSetActivityId function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestSetActivityId</b> method associates an activity identifier with an I/O request.

## Syntax

```
void WdfRequestSetActivityId(
  WDFREQUEST Request,
  LPGUID     ActivityId
);
```

## Parameters

`Request`

A handle to a framework request object.

`ActivityId`

A pointer to the activity identifier GUID to store in the I/O request.


## Return Value

This method does not return a value.

## Remarks

Calling <b>WdfRequestSetActivityId</b> does not set an association with any previously present activity identifier. When the driver calls <b>WdfRequestSetActivityId</b>, any existing activity identifier is overwritten.

To set an association, retrieve the existing identifier by calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn265621">WdfRequestRetrieveActivityId</a> and then associate the existing identifier with the new one by calling <a href="https://msdn.microsoft.com/798cf3ba-e1cc-4eaf-a1d2-2313a64aab1a">EventWriteTransfer</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265621">WdfRequestRetrieveActivityId</a>