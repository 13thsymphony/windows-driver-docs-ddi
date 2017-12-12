---
UID: NF.ndis.NdisFGetOptionalSwitchHandlers
title: NdisFGetOptionalSwitchHandlers function
author: windows-driver-content
description: Hyper-V extensible switch extensions call the NdisFGetOptionalSwitchHandlers function to obtain a list of pointers to the Hyper-V extensible switch handler functions.
old-location: netvista\ndisfgetoptionalswitchhandlers.htm
old-project: netvista
ms.assetid: bf034ecd-5c1b-4117-a7b0-bcca3971386b
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisFGetOptionalSwitchHandlers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFGetOptionalSwitchHandlers
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisFGetOptionalSwitchHandlers function



## -description

Hyper-V extensible switch extensions call the <b>NdisFGetOptionalSwitchHandlers</b> function to obtain a list of pointers to the Hyper-V extensible switch handler functions.





Hyper-V extensible switch extensions call the <b>NdisFGetOptionalSwitchHandlers</b> function to obtain a list of pointers to the Hyper-V extensible switch handler functions.





## -syntax

````
NDIS_STATUS NdisFGetOptionalSwitchHandlers(
  _In_    NDIS_HANDLE                    NdisFilterHandle,
  _Out_   PNDIS_SWITCH_CONTEXT           NdisSwitchContext,
  _Inout_ PNDIS_SWITCH_OPTIONAL_HANDLERS NdisSwitchHandlers
);
````


## -parameters

### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. When NDIS called the extension's  <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function, it passed this handle in the <i>NdisFilterHandle</i> parameter.


### -param NdisSwitchContext [out]

A pointer to the NDIS_SWITCH_CONTEXT value that identifies the extensible switch module to which the extension is attached. When  the  extension calls an extensible switch  handler  function, it must set the     <i>NdisSwitchContext</i> parameter to the value of this handle.


### -param NdisSwitchHandlers [in, out]

A pointer to a caller-allocated  <a href="netvista.ndis_switch_optional_handlers">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure. If the call succeeds, this structure will contain a list of pointers to the extensible switch handler functions.

For more information about these handler functions, see <a href="netvista.hyper_v_extensible_switch_handler_functions">Hyper-V Extensible Switch Handler Functions</a>.

<div class="alert"><b>Note</b>  Before the extension calls <b>NdisFGetOptionalSwitchHandlers</b>, it must initialize the <b>Header</b> member of the <a href="netvista.ndis_switch_optional_handlers">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure.</div>
<div> </div>

## -returns
If the call succeeds, <b>NdisFGetOptionalSwitchHandlers</b> returns NDIS_STATUS_SUCCESS. Otherwise, it returns NDIS_STATUS_NOT_SUPPORTED if the extensible switch extension is not bound to the underlying extensible switch component.




## -remarks
The  extension calls the <b>NdisFGetOptionalSwitchHandlers</b> function from its <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function. 

If the extension is installed with multiple <b>FilterMediaTypes</b> INF entries, the call to <b>NdisFGetOptionalSwitchHandlers</b> lets the extension  determine whether it is bound and attached to the driver stack for either the extensible switch or a physical network adapter. If the call returns NDIS_STATUS_SUCCESS, the extension is attached within the extensible switch driver stack. If the call returns NDIS_STATUS_NOT_SUPPORTED, the extension is attached within the driver stack for a physical network adapter.

For more information about <b>FilterMediaTypes</b> INF entries for extensible switch extensions, see <a href="netvista.inf_requirements_for_hyper_v_extensions">INF Requirements for Hyper-V Extensible Switch Extensions</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="netvista.ndis_switch_optional_handlers">NDIS_SWITCH_OPTIONAL_HANDLERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFGetOptionalSwitchHandlers function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

