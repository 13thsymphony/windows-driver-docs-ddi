---
UID: NC.ntddk.PSHED_PI_ENABLE_ERROR_SOURCE
title: PSHED_PI_ENABLE_ERROR_SOURCE
author: windows-driver-content
description: A PSHED plug-in's EnableErrorSource callback function enables an error source.
old-location: whea\enableerrorsource.htm
old-project: whea
ms.assetid: f2bc3b38-003e-4078-9bbd-d535e8971491
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
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
req.alt-api: EnableErrorSource
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

# PSHED_PI_ENABLE_ERROR_SOURCE callback



## -description
A PSHED plug-in's <i>EnableErrorSource</i> callback function enables an error source.



## -prototype

````
PSHED_PI_ENABLE_ERROR_SOURCE EnableErrorSource;

NTSTATUS EnableErrorSource(
  _Inout_opt_ PVOID                         PluginContext,
  _In_        PWHEA_ERROR_SOURCE_DESCRIPTOR ErrorSource
)
{ ... }
````


## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorSource [in]

A pointer to a <a href="whea.whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that is being enabled.


## -returns
A PSHED plug-in's <i>EnableErrorSource</i> callback function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The error source was successfully enabled.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The PSHED plug-in does not support enabling the specified error source.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>An error occurred.

 


## -remarks
A PSHED plug-in that participates in error source control sets the <b>Callbacks.SetErrorSourceInfo</b>, <b>Callbacks.EnableErrorSource</b>, and <b>Callbacks.DisableErrorSource</b> members of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="..\ntddk\nc-ntddk-pshed_pi_set_error_source_info.md">SetErrorSourceInfo</a>, <i>EnableErrorSource</i>, and <a href="..\ntddk\nc-ntddk-pshed_pi_disable_error_source.md">DisableErrorSource</a> callback functions when the plug-in calls the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorSourceControl</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to enable each of the error sources that were reported during error source discovery. The Windows kernel also calls into the PSHED to enable an error source in response to an error source enable request by a WHEA management application. If a PSHED plug-in is registered to participate in error source control, the PSHED calls the PSHED plug-in's <i>EnableErrorSource</i> callback function to give the PSHED plug-in an opportunity to enable the error source. If the <i>EnableErrorSource</i> callback function returns STATUS_NOT_SUPPORTED, the PSHED will enable the error source. Otherwise, the PSHED will just return the return value that is returned by the <i>EnableErrorSource</i> callback function.

If the PSHED plug-in successfully enables the error source, the PSHED will update the WHEA_ERROR_SOURCE_DESCRIPTOR structure on behalf of the PSHED plug-in after the call to the PSHED plug-in's <i>EnableErrorSource</i> callback function returns. A PSHED plug-in's <i>EnableErrorSource</i> callback function should not modify the error source descriptor.


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
<a href="..\ntddk\nc-ntddk-pshed_pi_disable_error_source.md">DisableErrorSource</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_set_error_source_info.md">SetErrorSourceInfo</a>
</dt>
<dt>
<a href="whea.whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_ENABLE_ERROR_SOURCE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

