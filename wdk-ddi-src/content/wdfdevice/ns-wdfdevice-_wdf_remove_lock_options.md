---
UID: NS.WDFDEVICE._WDF_REMOVE_LOCK_OPTIONS
title: _WDF_REMOVE_LOCK_OPTIONS
author: windows-driver-content
description: The WDF_REMOVE_LOCK_OPTIONS structure specifies options for acquiring a remove lock before delivering an IRP to the driver.
old-location: wdf\wdf_remove_lock_options.htm
old-project: wdf
ms.assetid: 0A50C1FB-D0C6-47C4-AD71-AD0B7486AA2E
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WDF_REMOVE_LOCK_OPTIONS
req.alt-loc: wdfdevice.h
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

# _WDF_REMOVE_LOCK_OPTIONS structure



## -description
<p class="CCE_Message">[Applies to KMDF only]

   The <b>WDF_REMOVE_LOCK_OPTIONS</b> structure specifies options for acquiring a remove lock before delivering an IRP to the driver.


## -syntax

````
typedef struct _WDF_REMOVE_LOCK_OPTIONS {
  ULONG Size;
  ULONG Flags;
} WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS;
````


## -struct-fields

### -field Size

The size of the structure, in bytes.

### -field Flags

The bitwise <b>OR</b> of values from the <a href="wdf.wdf_remove_lock_options_flags">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a> enumeration.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.11
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdeviceinitsetremovelockoptions">WdfDeviceInitSetRemoveLockOptions</a>
</dt>
<dt>
<a href="wdf.wdf_remove_lock_options_init">WDF_REMOVE_LOCK_OPTIONS_INIT</a>
</dt>
<dt>
<a href="wdf.wdf_remove_lock_options_flags">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REMOVE_LOCK_OPTIONS structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
