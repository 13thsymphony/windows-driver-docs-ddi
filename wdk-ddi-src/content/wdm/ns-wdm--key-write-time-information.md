---
UID: NS.wdm._KEY_WRITE_TIME_INFORMATION
title: KEY_WRITE_TIME_INFORMATION
author: windows-driver-content
description: The KEY_WRITE_TIME_INFORMATION structure is used by the system to set the last write time for a registry key.
old-location: kernel\key_write_time_information.htm
old-project: kernel
ms.assetid: 44f68a5a-c7ad-4555-b6b2-6461ac17960a
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KEY_WRITE_TIME_INFORMATION, KEY_WRITE_TIME_INFORMATION, *PKEY_WRITE_TIME_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KEY_WRITE_TIME_INFORMATION
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# KEY_WRITE_TIME_INFORMATION structure



## -description
<p>The <b>KEY_WRITE_TIME_INFORMATION</b> structure is used by the system to set the last write time for a registry key.</p>


## -syntax

````
typedef struct _KEY_WRITE_TIME_INFORMATION {
  LARGE_INTEGER LastWriteTime;
} KEY_WRITE_TIME_INFORMATION, *PKEY_WRITE_TIME_INFORMATION;
````


## -struct-fields
<dl>

### -field LastWriteTime

<dd>
<p>Specifies the last time that the key was changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available on Microsoft Windows XP and later versions of the Windows operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm--key-set-information-class.md">KEY_SET_INFORMATION_CLASS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_WRITE_TIME_INFORMATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
