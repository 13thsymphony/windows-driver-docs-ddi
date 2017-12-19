---
UID: NC.ntddk.PSHED_PI_GET_INJECTION_CAPABILITIES
title: PSHED_PI_GET_INJECTION_CAPABILITIES
author: windows-driver-content
description: A PSHED plug-in's GetInjectionCapabilities callback function returns an error injection capabilities union that describes the types of hardware errors that can be injected into the hardware platform.
old-location: whea\getinjectioncapabilities.htm
old-project: whea
ms.assetid: 8cb19677-11b8-4594-b4dd-ebd00fae07d4
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
req.alt-api: GetInjectionCapabilities
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

# PSHED_PI_GET_INJECTION_CAPABILITIES callback



## -description
A PSHED plug-in's <i>GetInjectionCapabilities</i> callback function returns an error injection capabilities union that describes the types of hardware errors that can be injected into the hardware platform.



## -prototype

````
PSHED_PI_GET_INJECTION_CAPABILITIES GetInjectionCapabilities;

NTSTATUS GetInjectionCapabilities(
  _Inout_opt_ PVOID                              PluginContext,
  _Out_       PWHEA_ERROR_INJECTION_CAPABILITIES Capabilities
)
{ ... }
````


## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param Capabilities [out]

A pointer to a <a href="whea.whea_error_injection_capabilities">WHEA_ERROR_INJECTION_CAPABILITIES</a> union. This union receives the data that describes the types of hardware errors that can be injected into the hardware platform.


## -returns
A PSHED plug-in's <i>GetInjectionCapabilities</i> callback function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The data that describes the types of hardware errors that can be injected into the hardware platform was successfully returned in the WHEA_ERROR_INJECTION_CAPABILITIES union pointed to by the <i>Capabilities</i> parameter.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>An error occurred.

 


## -remarks
A PSHED plug-in that participates in error injection sets the <b>Callbacks.GetInjectionCapabilities </b>and <b>Callbacks.InjectError </b>members of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>GetInjectionCapabilities</i> and <a href="..\ntddk\nc-ntddk-pshed_pi_inject_error.md">InjectError</a> callback functions when the plug-in calls the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorInjection</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to retrieve information about the types of hardware errors that can be injected into the hardware platform in response to an error injection capabilities inquiry by a WHEA management application. If a PSHED plug-in is registered to participate in error injection, the PSHED calls the PSHED plug-in's <i>GetInjectionCapabilities</i> callback function to retrieve information about additional types of hardware errors that can be injected into the hardware platform.


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
<a href="..\ntddk\nc-ntddk-pshed_pi_inject_error.md">InjectError</a>
</dt>
<dt>
<a href="whea.whea_error_injection_capabilities">WHEA_ERROR_INJECTION_CAPABILITIES</a>
</dt>
<dt>
<a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_GET_INJECTION_CAPABILITIES callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

