---
UID: NF.mrx.RxFsdDispatch
title: RxFsdDispatch function
author: windows-driver-content
description: RxFsdDispatch implements the file system driver (FSD) dispatch for RDBSS to process an I/O request packet (IRP).
old-location: ifsk\rxfsddispatch.htm
old-project: ifsk
ms.assetid: 92b9b22a-0fe7-4c95-a4fc-5f5f5558b4cf
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxFsdDispatch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrx.h
req.include-header: Mrx.h, Rxstruc.h, Struchdr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxFsdDispatch
req.alt-loc: mrx.h
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
---

# RxFsdDispatch function



## -description
<b>RxFsdDispatch</b> implements the file system driver (FSD) dispatch for RDBSS to process an I/O request packet (IRP). A pointer to this routine is copied over the device driver dispatch table for the network mini-redirector driver by the <b>RxDriverEntry</b> routine when RDBSS is initialized. 


## -syntax

````
NTSTATUS RxFsdDispatch(
  _In_ PRDBSS_DEVICE_OBJECT RxDeviceObject,
  _In_ PIRP                 Irp
);
````


## -parameters

### -param RxDeviceObject [in]

A pointer to the RDBSS device object for this network mini-redirector.

### -param Irp [in]

A pointer to the I/O request packet being processed.

## -returns
<b>RxFsdDispatch</b> returns one of the following values: 
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>A request was made on an invalid device object. For example, this error is returned if a file system object is passed as the <i>RxDeviceObject</i> parameter. This status value indicates failure.
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>An invalid request was made to create a named pipe or a mailslot (the <b>MajorFunction</b> member of the <i>Irp</i> was IRP_MJ_CREATE_MAILSLOT or IRP_MJ_CREATE_NAMED_PIPE). This status value indicates failure.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>An asynchronous request was made and the status of the request is pending.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The <b>RxFsdDispatch</b> routine call was successful.

 

## -remarks
<b>RxFsdDispatch</b> is called by RDBSS to process an I/O request packet (IRP). These IRPs are normally received by RDBSS in response to a user-mode application requesting operations on a file. It is also possible for another kernel driver to issue such an IRP. 

A pointer to <b>RxFsdDispatch</b> routine is copied over the driver dispatch table for a network mini-redirector driver when the <b>RxDriverEntry</b> routine is called to initialize RDBSS. 

Internally, RDBSS maintains two dispatch vectors:

A common dispatch vector for most operations.

A private dispatch vector for file device FCB operations.

If the IRP is an IRP_MJ_CREATE request, then <b>RxFsdDispatch</b> will use a common dispatch vector. If the IRP is for an operation on an FCB of a file object, <b>RxFsdDispatch</b> will check if a private dispatch vector should be used. Otherwise a common dispatch vector will be used to process the IRP. 

<b>RxFsdDispatch</b> calls internal routines to process the standard IRPs most of which result in a call to one of the callback routines implemented by the network mini-redirector driver. 

A few IRPs are treated as special and handled internally by RDBSS. For example, the IRP_MJ_SYSTEM_CONTROL is used internally if WMI is enabled. IRP_MJ_CREATE_MAILSLOT or IRP_MJ_CREATE_NAMED_PIPE requests are treated specially and rejected (a STATUS_OBJECT_NAME_INVALID error is returned). 

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
<dt>Mrx.h (include Mrx.h, Rxstruc.h, or Struchdr.h)</dt>
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
<a href="ifsk.rxdriverentry">RxDriverEntry</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFsdDispatch routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
