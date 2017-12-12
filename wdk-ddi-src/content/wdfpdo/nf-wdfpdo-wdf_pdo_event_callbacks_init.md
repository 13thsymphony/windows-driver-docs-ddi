---
UID: NF.wdfpdo.WDF_PDO_EVENT_CALLBACKS_INIT
title: WDF_PDO_EVENT_CALLBACKS_INIT function
author: windows-driver-content
description: The WDF_PDO_EVENT_CALLBACKS_INIT function initializes a WDF_PDO_EVENT_CALLBACKS structure.
old-location: wdf\wdf_pdo_event_callbacks_init.htm
old-project: wdf
ms.assetid: f3e0ee33-42cd-4544-aad2-c353f7c30675
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_PDO_EVENT_CALLBACKS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_PDO_EVENT_CALLBACKS_INIT
req.alt-loc: wdfpdo.h
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

# WDF_PDO_EVENT_CALLBACKS_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_PDO_EVENT_CALLBACKS_INIT</b> function initializes a <a href="wdf.wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure.



## -syntax

````
VOID WDF_PDO_EVENT_CALLBACKS_INIT(
  _Out_ PWDF_PDO_EVENT_CALLBACKS Callbacks
);
````


## -parameters

### -param Callbacks [out]

A pointer to the driver's <a href="wdf.wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure. 


## -returns
None


## -remarks
The <b>WDF_PDO_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="wdf.wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure and sets the structure's <b>Size</b> member.

For a code example that uses <b>WDF_PDO_EVENT_CALLBACKS_INIT</b>, see <a href="wdf.wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfpdo.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a>
</dt>
<dt>
<a href="wdf.wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_PDO_EVENT_CALLBACKS_INIT function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

