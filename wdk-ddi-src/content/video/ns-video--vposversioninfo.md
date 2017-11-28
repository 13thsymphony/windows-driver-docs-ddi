---
UID: NS.video._VPOSVERSIONINFO
title: VPOSVERSIONINFO
author: windows-driver-content
description: The VPOSVERSIONINFO structure contains version information about the currently running operating system.
old-location: display\vposversioninfo.htm
old-project: display
ms.assetid: b6335df5-81d9-4a00-8e97-0ebebb987d32
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VPOSVERSIONINFO, VPOSVERSIONINFO, *PVPOSVERSIONINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VPOSVERSIONINFO
req.alt-loc: video.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.iface: 
req.product: Windows 10 or later.
---

# VPOSVERSIONINFO structure



## -description
<p>The VPOSVERSIONINFO structure contains version information about the currently running operating system.</p>


## -syntax

````
typedef struct _VPOSVERSIONINFO {
  IN ULONG   Size;
  OUT ULONG  MajorVersion;
  OUT ULONG  MinorVersion;
  OUT ULONG  BuildNumber;
  OUT USHORT ServicePackMajor;
  OUT USHORT ServicePackMinor;
} VPOSVERSIONINFO, *PVPOSVERSIONINFO;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>Specifies the size, in bytes, of the VPOSVERSIONINFO structure.</p>
</dd>

### -field <b>MajorVersion</b>

<dd>
<p>Specifies the major version number of the operating system. For example, for Windows 2000, the major version number is five. For Windows XP, the major version number is six.</p>
</dd>

### -field <b>MinorVersion</b>

<dd>
<p>Specifies the minor version number of the operating system. For example, for Windows 2000, the minor version number is zero.</p>
</dd>

### -field <b>BuildNumber</b>

<dd>
<p>Specifies the build number of the operating system.</p>
</dd>

### -field <b>ServicePackMajor</b>

<dd>
<p>Specifies the major version number of the latest Service Pack installed on the operating system. For example, for Service Pack 3, the major version number is three.</p>
</dd>

### -field <b>ServicePackMinor</b>

<dd>
<p>Specifies the minor version number of the latest Service Pack installed on the operating system. For example, for Service Pack 3, the minor version number is zero.</p>
</dd>
</dl>

## -remarks
<p>This structure is available in Windows XP and later.</p>

<p>To obtain version information about the currently running operating system, a video miniport driver would call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570318">VideoPortGetVersion</a> function, which fills in this structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570318">VideoPortGetVersion</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VPOSVERSIONINFO structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
