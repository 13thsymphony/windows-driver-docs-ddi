---
UID: NS.ntddsysenv._XVARIABLE_NAME
title: XVARIABLE_NAME
author: windows-driver-content
description: Stores the name of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES request.
old-location: kernel\xvariable_name.htm
ms.assetid: DF02AB1E-6803-492C-9261-400177497195
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntddsysenv.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: XVARIABLE_NAME
req.alt-loc: Ntddsysenv.h
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
ms.keywords: XVARIABLE_NAME, XVARIABLE_NAME, *PXVARIABLE_NAME
req.iface: 
---

# XVARIABLE_NAME structure



## -description
<p>Stores the name of a system environment variable using
    SysEnv device. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791525">IOCTL_SYSENV_ENUM_VARIABLES</a> request.</p>


## -syntax

````
typedef struct _XVARIABLE_NAME {
  ULONG NextEntryOffset;
  GUID  VendorGuid;
  WCHAR Name[ANYSIZE_ARRAY];
} XVARIABLE_NAME, *PXVARIABLE_NAME;
````


## -struct-fields
<dl>

### -field <b>NextEntryOffset</b>

<dd>
<p>The location of the next entry in the array of <b>XVARIABLE_NAME</b> structures reprieved by the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt791525">IOCTL_SYSENV_ENUM_VARIABLES</a> request.</p>
</dd>

### -field <b>VendorGuid</b>

<dd>
<p>The vendor GUID.</p>
</dd>

### -field <b>Name</b>

<dd>
<p>Name of the system environment variable.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddsysenv.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt791525">IOCTL_SYSENV_ENUM_VARIABLES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20XVARIABLE_NAME structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
