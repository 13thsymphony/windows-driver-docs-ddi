---
UID: NC.ntddk.PSHED_PI_CLEAR_ERROR_RECORD
title: PSHED_PI_CLEAR_ERROR_RECORD
author: windows-driver-content
description: A PSHED plug-in's ClearErrorRecord callback function clears the specified error record from the system's persistent data storage.
old-location: whea\clearerrorrecord.htm
old-project: whea
ms.assetid: e9893f9c-7fbd-4a02-8c2d-d7c480ed5198
ms.author: windowsdriverdev
ms.date: 12/5/2017
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClearErrorRecord
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# PSHED_PI_CLEAR_ERROR_RECORD callback



## -description
A PSHED plug-in's <i>ClearErrorRecord </i>callback function clears the specified error record from the system's persistent data storage.


## -prototype

````
PSHED_PI_CLEAR_ERROR_RECORD ClearErrorRecord;

NTSTATUS ClearErrorRecord(
  _Inout_opt_ PVOID     PluginContext,
  _In_        ULONG     Flags,
  _In_        ULONGLONG ErrorRecordId
)
{ ... }
````


## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.

### -param Flags [in]

A bit-wise OR'ed combination of flags that affect the clear operation. No flags are currently defined.

### -param ErrorRecordId [in]

The identifier of the error record that is being cleared from the system's persistent data storage. This identifier should be compared to the <b>Header.RecordId</b> member of each <a href="whea.whea_error_record">WHEA_ERROR_RECORD</a> structure that has been written to the system's persistent data storage to identify the error record to be cleared.

## -returns
A PSHED plug-in's <i>ClearErrorRecord</i> callback function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The error record was successfully cleared from the system's persistent data storage.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>An error occurred.

 

## -remarks
A PSHED plug-in that participates in error record persistence sets the <b>Callbacks.WriteErrorRecord</b>, <b>Callbacks.ReadErrorRecord </b>and <b>Callbacks.ClearErrorRecord </b>members of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="..\ntddk\nc-ntddk-pshed_pi_write_error_record.md">WriteErrorRecord</a>, <a href="..\ntddk\nc-ntddk-pshed_pi_read_error_record.md">ReadErrorRecord</a>, and <i>ClearErrorRecord</i> callback functions when the plug-in calls the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorRecordPersistence</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to clear an error record from the system's persistent data storage. If a PSHED plug-in is registered to participate in error record persistence, the PSHED calls the PSHED plug-in's <i>ClearErrorRecord</i> callback function to perform the clear operation. The mechanism that is used to clear the error record from the system's persistent data storage is platform-specific.

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
Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="whea.pshedregisterplugin">PshedRegisterPlugin</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_read_error_record.md">ReadErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_write_error_record.md">WriteErrorRecord</a>
</dt>
<dt>
<a href="whea.whea_error_record">WHEA_ERROR_RECORD</a>
</dt>
<dt>
<a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_CLEAR_ERROR_RECORD callback function%20 RELEASE:%20(12/5/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
