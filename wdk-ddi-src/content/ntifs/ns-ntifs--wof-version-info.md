---
UID: NS.ntifs._WOF_VERSION_INFO
title: WOF_VERSION_INFO
author: windows-driver-content
description: The WOF_VERSION_INFO structure contains the version corresponding to the driver supporting a given provider.
old-location: ifsk\wof_version_info.htm
old-project: ifsk
ms.assetid: 953F34FC-2E8F-4569-89B8-2F9541456F3B
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: WOF_VERSION_INFO, WOF_VERSION_INFO, *PWOF_VERSION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WOF_VERSION_INFO
req.alt-loc: Ntifs.h
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
req.iface: 
---

# WOF_VERSION_INFO structure



## -description
<p>The <b>WOF_VERSION_INFO</b> structure contains the version corresponding to the driver supporting a given provider.</p>


## -syntax

````
typedef struct _WOF_VERSION_INFO {
  ULONG WofVersion;
} WOF_VERSION_INFO, *PWOF_VERSION_INFO;
````


## -struct-fields
<dl>

### -field <b>WofVersion</b>

<dd>
<p>The version of the WOF driver. This value includes the major and minor version numbers of the operating system in the high-order word, and the build number of the operating system in the low-order word. The major version can be extracted with HIBYTE(HIWORD(<i>WofVersion</i>)); the minor version can be extracted with LOBYTE(HIWORD(<i>WofVersion</i>)); the build number can be extracted with LOWORD(<i>WofVersion</i>). </p>
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
<p>Available starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fsctl_get_wof_version">FSCTL_GET_WOF_VERSION</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--wof-external-file-id.md">WOF_EXTERNAL_FILE_ID</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--wof-external-info.md">WOF_EXTERNAL_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20WOF_VERSION_INFO structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
