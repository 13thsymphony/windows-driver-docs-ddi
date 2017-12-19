---
UID: NS.NTDDK._WHEA_PSHED_PLUGIN_CALLBACKS
title: _WHEA_PSHED_PLUGIN_CALLBACKS
author: windows-driver-content
description: The WHEA_PSHED_PLUGIN_CALLBACKS structure describes the callback functions for a PSHED plug-in.
old-location: whea\whea_pshed_plugin_callbacks.htm
old-project: whea
ms.assetid: 3b99f2bf-0ebc-40b2-a586-acc89200132b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_PSHED_PLUGIN_CALLBACKS, PWHEA_PSHED_PLUGIN_CALLBACKS, WHEA_PSHED_PLUGIN_CALLBACKS, *PWHEA_PSHED_PLUGIN_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_PSHED_PLUGIN_CALLBACKS
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _WHEA_PSHED_PLUGIN_CALLBACKS structure



## -description
The WHEA_PSHED_PLUGIN_CALLBACKS structure describes the callback functions for a PSHED plug-in.



## -syntax

````
typedef struct _WHEA_PSHED_PLUGIN_CALLBACKS {
  PSHED_PI_GET_ALL_ERROR_SOURCES      GetAllErrorSources;
  PVOID                               Reserved;
  PSHED_PI_GET_ERROR_SOURCE_INFO      GetErrorSourceInfo;
  PSHED_PI_SET_ERROR_SOURCE_INFO      SetErrorSourceInfo;
  PSHED_PI_ENABLE_ERROR_SOURCE        EnableErrorSource;
  PSHED_PI_DISABLE_ERROR_SOURCE       DisableErrorSource;
  PSHED_PI_WRITE_ERROR_RECORD         WriteErrorRecord;
  PSHED_PI_READ_ERROR_RECORD          ReadErrorRecord;
  PSHED_PI_CLEAR_ERROR_RECORD         ClearErrorRecord;
  PSHED_PI_RETRIEVE_ERROR_INFO        RetrieveErrorInfo;
  PSHED_PI_FINALIZE_ERROR_RECORD      FinalizeErrorRecord;
  PSHED_PI_CLEAR_ERROR_STATUS         ClearErrorStatus;
  PSHED_PI_ATTEMPT_ERROR_RECOVERY     AttemptRecovery;
  PSHED_PI_GET_INJECTION_CAPABILITIES GetInjectionCapabilities;
  PSHED_PI_INJECT_ERROR               InjectError;
} WHEA_PSHED_PLUGIN_CALLBACKS, *PWHEA_PSHED_PLUGIN_CALLBACKS;
````


## -struct-fields

### -field GetAllErrorSources

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_get_all_error_sources.md">GetAllErrorSources</a> callback function. If a PSHED plug-in does not participate in error source discovery, this member should be set to <b>NULL</b>.


### -field Reserved

Reserved for system use. This member should be set to <b>NULL</b>.


### -field GetErrorSourceInfo

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_get_error_source_info.md">GetErrorSourceInfo</a> callback function. If a PSHED plug-in does not participate in error source discovery, this member should be set to <b>NULL</b>.


### -field SetErrorSourceInfo

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_set_error_source_info.md">SetErrorSourceInfo</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.


### -field EnableErrorSource

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_enable_error_source.md">EnableErrorSource</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.


### -field DisableErrorSource

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_disable_error_source.md">DisableErrorSource</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.


### -field WriteErrorRecord

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_write_error_record.md">WriteErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.


### -field ReadErrorRecord

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_read_error_record.md">ReadErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.


### -field ClearErrorRecord

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_record.md">ClearErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.


### -field RetrieveErrorInfo

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_retrieve_error_info.md">RetrieveErrorInfo</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.


### -field FinalizeErrorRecord

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_finalize_error_record.md">FinalizeErrorRecord</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.


### -field ClearErrorStatus

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_status.md">ClearErrorStatus</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.


### -field AttemptRecovery

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_attempt_error_recovery.md">AttemptRecovery</a> callback function. If a PSHED plug-in does not participate in error recovery, this member should be set to <b>NULL</b>.


### -field GetInjectionCapabilities

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_get_injection_capabilities.md">GetInjectionCapabilities</a> callback function. If a PSHED plug-in does not participate in error injection, this member should be set to <b>NULL</b>.


### -field InjectError

A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed_pi_inject_error.md">InjectError</a> callback function. If a PSHED plug-in does not participate in error injection, this member should be set to <b>NULL</b>.


## -remarks
A WHEA_PSHED_PLUGIN_CALLBACKS structure is contained within the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure.


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_attempt_error_recovery.md">AttemptRecovery</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_record.md">ClearErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_status.md">ClearErrorStatus</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_disable_error_source.md">DisableErrorSource</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_enable_error_source.md">EnableErrorSource</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_finalize_error_record.md">FinalizeErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_get_all_error_sources.md">GetAllErrorSources</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_get_error_source_info.md">GetErrorSourceInfo</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_get_injection_capabilities.md">GetInjectionCapabilities</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_inject_error.md">InjectError</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_read_error_record.md">ReadErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_retrieve_error_info.md">RetrieveErrorInfo</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_set_error_source_info.md">SetErrorSourceInfo</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_write_error_record.md">WriteErrorRecord</a>
</dt>
<dt>
<a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PSHED_PLUGIN_CALLBACKS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

