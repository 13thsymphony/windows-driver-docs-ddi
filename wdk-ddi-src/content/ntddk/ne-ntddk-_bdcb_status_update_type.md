---
UID: NE.ntddk._BDCB_STATUS_UPDATE_TYPE
title: _BDCB_STATUS_UPDATE_TYPE
author: windows-driver-content
description: The BDCB_STATUS_UPDATE_TYPE enumeration lists the types of boot-driver callback status updates.
old-location: kernel\bdcb_status_update_type.htm
old-project: kernel
ms.assetid: E18AD58C-74D0-4CA7-9EE5-F96863F88E26
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BDCB_STATUS_UPDATE_TYPE, BDCB_STATUS_UPDATE_TYPE, *PBDCB_STATUS_UPDATE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDCB_STATUS_UPDATE_TYPE
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
req.irql: 
---

# _BDCB_STATUS_UPDATE_TYPE enumeration



## -description
The BDCB_STATUS_UPDATE_TYPE enumeration lists the types of boot-driver callback status updates.


## -syntax

````
typedef enum _BDCB_STATUS_UPDATE_TYPE { 
  BdCbStatusPrepareForDependecyLoad,
  BdCbStatusPrepareForDriverLoad,
  BdCbStatusPrepareForUnload
} BDCB_STATUS_UPDATE_TYPE;
````


## -enum-fields

### -field BdCbStatusPrepareForDependecyLoad

Windows will start loading driver dependencies next.

### -field BdCbStatusPrepareForDriverLoad

Windows has completed loading driver dependencies and will start loading boot-start drivers.

### -field BdCbStatusPrepareForUnload

Windows has completed the initialization of all boot-start drivers. After the completion of this callback, the Boot Driver Callback Facility will be torn down and no more callbacks will be received. During this callback, Early Launch AM drivers must clean up and prepare to be unloaded.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with  Windows 8.
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
<a href="kernel.bdcb_status_update_context">BDCB_STATUS_UPDATE_CONTEXT</a>
</dt>
<dt>
<a href="kernel.ioregisterbootdrivercallback">BOOT_DRIVER_CALLBACK_FUNCTION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BDCB_STATUS_UPDATE_TYPE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
