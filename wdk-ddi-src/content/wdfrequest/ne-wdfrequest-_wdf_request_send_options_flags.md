---
UID: NE.wdfrequest._WDF_REQUEST_SEND_OPTIONS_FLAGS
title: _WDF_REQUEST_SEND_OPTIONS_FLAGS
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_flags.htm
old-project: wdf
ms.assetid: 68be1034-62f0-4444-b4c9-097277a7561f
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_REQUEST_SEND_OPTIONS_FLAGS, WDF_REQUEST_SEND_OPTIONS_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_REQUEST_SEND_OPTIONS_FLAGS
req.alt-loc: wdfrequest.h
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
req.product: Windows 10 or later.
---

# _WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_REQUEST_SEND_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -syntax

````
typedef enum _WDF_REQUEST_SEND_OPTIONS_FLAGS { 
  WDF_REQUEST_SEND_OPTION_TIMEOUT                       = 0x0000001,
  WDF_REQUEST_SEND_OPTION_SYNCHRONOUS                   = 0x0000002,
  WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE           = 0x0000004,
  WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET               = 0x0000008,
  WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT            = 0x00010000,
  WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE  = 0x00020000
} WDF_REQUEST_SEND_OPTIONS_FLAGS;
````


## -enum-fields

### -field WDF_REQUEST_SEND_OPTION_TIMEOUT

If the driver sets this flag, the <b>Timeout</b> member of the WDF_REQUEST_SEND_OPTIONS structure is valid.

### -field WDF_REQUEST_SEND_OPTION_SYNCHRONOUS

If the driver sets this flag, the framework handles the associated I/O request synchronously. (The driver does not have to set this flag if it is calling an object method whose name ends with "Synchronously", such as <a href="wdf.wdfiotargetsendreadsynchronously">WdfIoTargetSendReadSynchronously</a>.)

### -field WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE

If the driver sets this flag, the framework sends the I/O request to the I/O target, regardless of the I/O target's state. If not set, the framework queues the request if the target is stopped. Setting this flag allows a driver to send a request, such as a request to reset a USB pipe, to a device after the driver has called <a href="wdf.wdfiotargetstop">WdfIoTargetStop</a>.

### -field WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET

If the driver sets this flag, the driver is sending the request asynchronously and does not need to be notified when the request is completed or canceled. The framework sends the I/O request to the I/O target, regardless of the I/O target's state. The driver does not set a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function or call <a href="wdf.wdfrequestcomplete">WdfRequestComplete</a> for the request. If the driver sets this flag, it cannot set any other flags. For more information about this flag, see the following Remarks section.

### -field WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT

This flag applies to UMDF only. If set, and if the I/O request type is <b>WdfRequestTypeCreate</b>, the <a href="wdf.wdfrequestsend">WdfRequestSend</a> method attempts to pass the client's impersonation level to the driver's I/O target. The <b>WdfRequestSend</b> method returns an error code if the impersonation attempt fails, unless the driver also sets the <b>WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE</b> flag.

### -field WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE

This flag applies to UMDF only. If set, the framework still sends the request even if impersonation fails.  You can use this value only with <b>WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT</b>.

## -remarks
A driver that sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag typically does not format the I/O request before it calls <a href="wdf.wdfrequestsend">WdfRequestSend</a> to send the request to an I/O target. In fact, a driver that sets this flag must not call any of the <b>WdfIoTargetFormatRequestFor</b><i>Xxx</i> methods before it calls <b>WdfRequestSend</b>. The driver can use only the <a href="wdf.wdfrequestformatrequestusingcurrenttype">WdfRequestFormatRequestUsingCurrentType</a> or <a href="wdf.wdfrequestwdmformatusingstacklocation">WdfRequestWdmFormatUsingStackLocation</a> method to format the request.

Your driver <i>cannot</i> set the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag in the following situations:

The driver created the request object by calling <a href="wdf.wdfrequestcreate">WdfRequestCreate</a>.

The driver is sending the I/O request to a remote I/O target and the driver specified the <a href="wdf.wdf_io_target_open_type">WdfIoTargetOpenByName</a> flag when it called <a href="wdf.wdfiotargetopen">WdfIoTargetOpen</a>.

The driver is sending the I/O request to a remote I/O target, and the driver specified both the <a href="wdf.wdf_io_target_open_type">WdfIoTargetOpenUseExistingDevice</a> flag and a <a href="wdf.wdf_io_target_open_params">TargetFileObject</a> pointer when it called <a href="wdf.wdfiotargetopen">WdfIoTargetOpen</a>.

The request type is <a href="wdf.wdf_request_type">WdfRequestTypeCreate</a> and the driver has not set the <a href="wdf.wdf_fileobject_class">WdfFileObjectNotRequired</a> flag. (For more information about this situation, see <a href="wdf.framework_file_objects">Framework File Objects</a>.)

For the UMDF version of this enumeration, see <a href="wdf.wdf_request_send_options_flags__umdf_">WDF_REQUEST_SEND_OPTIONS_FLAGS (UMDF)</a>.

## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfrequest.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfiotargetstop">WdfIoTargetStop</a>
</dt>
<dt>
<a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
