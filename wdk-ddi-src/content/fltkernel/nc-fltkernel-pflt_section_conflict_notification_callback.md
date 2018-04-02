---
UID: NC:fltkernel.PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK
title: PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK
author: windows-driver-content
description: A minifilter driver can optionally register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's SectionNotificationCallback routine.
old-location: ifsk\pflt_section_conflict_notification_callback.htm
old-project: ifsk
ms.assetid: 22840772-7DFC-4339-9C06-4900E47048B4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK, SectionNotificationCallback, SectionNotificationCallback routine [Installable File System Drivers], fltkernel/SectionNotificationCallback, ifsk.pflt_section_conflict_notification_callback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: The PFLT_CONTEXT_ALLOCATE_CALLBACK callback routine is available on Windows 8 and later.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	SectionNotificationCallback
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK callback function
A minifilter driver can optionally register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's <i>SectionNotificationCallback</i> routine. Certain file operations are incompatible with file sections. If a minifilter provides a <i>SectionNotificationCallback</i> routine, the callback is called when section conflicts occur.

## Syntax

```
PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK PfltSectionConflictNotificationCallback;

NTSTATUS PfltSectionConflictNotificationCallback(
  PFLT_INSTANCE Instance,
  PFLT_CONTEXT SectionContext,
  PFLT_CALLBACK_DATA Data
)
{...}
```

## Parameters

`Instance`

An opaque instance pointer to the minifilter driver instance that is initiating the I/O operation.

`SectionContext`

A pointer to the section context that incurred a data scan section conflict.

`Data`

A pointer to a caller-allocated structure that contains the callback data.


## Return Value

This callback routine returns STATUS_SUCCESS.

## Remarks

A minifilter registers for section conflict notifications by setting a <i>PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK</i> routine to the <b>SectionNotificationCallback</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure when registering a minifilter driver.

Certain situations can occur where holding a section open is incompatible with current file I/O. In particular, file I/O that triggers a cache purge can cause cache incoherency if the cache purge is prevented because of an open section.  A minifilter can provide this optional callback routine for notifications of these events. When a notification is received, the section can be closed to allow the conflicting I/O operation to continue.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PFLT_CONTEXT_ALLOCATE_CALLBACK callback routine is available on Windows 8 and later.  |
| **Target Platform** | Desktop |
| **Header** | fltkernel.h (include Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450937">FltCreateSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>