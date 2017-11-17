---
UID: NF.ucmmanager.UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
title: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
author: windows-driver-content
description: Initializes a UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure.
old-location: buses\ucm_connector_typec_attach_params_init.htm
ms.assetid: C360556B-5A28-4FC3-9304-6000061A1D69
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: usbref
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
req.alt-loc: Ucmmanager.h
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
ms.keywords: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
req.iface: 
req.product: Windows 10 or later.
---

# UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function



## -description
<p>Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187928">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a> structure.</p>


## -syntax

````
FORCEINLINE void UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT(
  _Out_ PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS Config,
  _In_  UCM_TYPE_C_PORT_STATE              PortPartnerType
);
````


## -parameters
<dl>

### -param <i>Config</i> [out]

<dd>
<p>Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt187928">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a> structure to initialize.</p>
</dd>

### -param <i>PortPartnerType</i> [in]

<dd>
<p>A <a href="https://msdn.microsoft.com/4779E943-5C13-4DE2-AF8F-37657F0F99C0">UCM_TYPE_C_PORT_STATE</a>-typed flag that indicates the state of the partner port.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucmmanager.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187915">UcmConnectorTypeCAttach</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
