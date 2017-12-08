---
UID: NF.rxprocs.RxLogEventDirect
title: RxLogEventDirect function
author: windows-driver-content
description: RxLogEventDirect is called to log an error to the I/O error log. It is recommended that the RXLogEvent macro or the RxLogFailure macro be used instead of calling this routine directly.
old-location: ifsk\rxlogeventdirect.htm
old-project: ifsk
ms.assetid: fc0bf8c4-cc0b-4f1e-bd4e-facf8f0d2a96
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxLogEventDirect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h, Rxstruc.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxLogEventDirect
req.alt-loc: rxprocs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# RxLogEventDirect function



## -description
<b>RxLogEventDirect</b> is called to log an error to the I/O error log. 
It is recommended that the RXLogEvent macro or the RxLogFailure macro be used instead of calling this routine directly.


## -syntax

````
VOID RxLogEventDirect(
  _In_ PRDBSS_DEVICE_OBJECT DeviceObject,
  _In_ PUNICODE_STRING      OriginatorId,
  _In_ ULONG                EventId,
  _In_ NTSTATUS             Status,
  _In_ ULONG                Line
);
````


## -parameters

### -param DeviceObject [in]

A pointer to the RDBSS device object.

### -param OriginatorId [in]

A string indicating the caller generating the error.

### -param EventId [in]

The value indicating the I/O error log code value which is different than an NTSTATUS value returned by a routine. The legal I/O error log code values are defined in the <i>ntiolog.h</i> header file included with the Microsoft Windows SDK and Visual Studio.

### -param Status [in]

The value indicating the status code of a routine indicating a failure.

### -param Line [in]

The line number in the source code file where this failure occurred.

## -returns
None

## -remarks
<b>RxLogEventDirect</b> internally calls the <b>RxLogEventWithAnnotation</b> routine to create and write the log entry. 

The I/O error log entry size is limited to a length of 255 characters. So if the combined length of the <i>OriginatorId</i> plus the size of the fixed part of the I/O error log exceeds 255, then no I/O error log entry will be created.

The <b>RxLogEventWithAnnotation</b> routine needs to allocate memory in order to create the I/O error log entry . Consequently, <b>RxLogEventDirect</b> can silently fail if the memory allocation fails. 

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
Header
</th>
<td width="70%">
<dl>
<dt>Rxprocs.h (include Rxprocs.h or Rxstruc.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rxlogeventwithannotation">RxLogEventWithAnnotation</a>
</dt>
<dt>
<a href="ifsk.rxlogeventwithbufferdirect">RxLogEventWithBufferDirect</a>
</dt>
<dt>
<a href="ifsk._rxlog">_RxLog</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxLogEventDirect routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
