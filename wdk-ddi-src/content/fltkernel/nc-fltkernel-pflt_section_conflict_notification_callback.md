---
UID: NC.fltkernel.PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK
title: PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK
author: windows-driver-content
description: A minifilter driver can optionally register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's SectionNotificationCallback routine.
old-location: ifsk\pflt_section_conflict_notification_callback.htm
old-project: ifsk
ms.assetid: 22840772-7DFC-4339-9C06-4900E47048B4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: DrvPopulateFilterServices
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
req.alt-api: SectionNotificationCallback
req.alt-loc: fltkernel.h
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
---

# PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK callback



## -description
A minifilter driver can optionally register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's <i>SectionNotificationCallback</i> routine. Certain file operations are incompatible with file sections. If a minifilter provides a <i>SectionNotificationCallback</i> routine, the callback is called when section conflicts occur.



## -prototype

````
PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK SectionNotificationCallback;

NTSTATUS SectionNotificationCallback(
  _In_ PFLT_INSTANCE      Instance,
  _In_ PFLT_CONTEXT       SectionContext,
  _In_ PFLT_CALLBACK_DATA Data
)
{ ... }
````


## -parameters

### -param Instance [in]

An opaque instance pointer to the minifilter driver instance that is initiating the I/O operation.


### -param SectionContext [in]

A pointer to the section context that incurred a data scan section conflict.


### -param Data [in]

A pointer to a caller-allocated structure that contains the callback data.


## -returns
This callback routine returns STATUS_SUCCESS.


## -remarks
A minifilter registers for section conflict notifications by setting a <i>PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK</i> routine to the <b>SectionNotificationCallback</b> member of the <a href="ifsk.flt_registration">FLT_REGISTRATION</a> structure when registering a minifilter driver.

Certain situations can occur where holding a section open is incompatible with current file I/O. In particular, file I/O that triggers a cache purge can cause cache incoherency if the cache purge is prevented because of an open section.  A minifilter can provide this optional callback routine for notifications of these events. When a notification is received, the section can be closed to allow the conflicting I/O operation to continue.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
The PFLT_CONTEXT_ALLOCATE_CALLBACK callback routine is available on Windows 8 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="ifsk.flt_registration">FLT_REGISTRATION</a>
</dt>
<dt>
<a href="ifsk.fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>
</dt>
<dt>
<a href="ifsk.fltregisterfilter">FltRegisterFilter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

