---
UID: NS.pep_x._PEP_PPM_QUERY_LP_SETTINGS
title: PEP_PPM_QUERY_LP_SETTINGS
author: windows-driver-content
description: The PEP_PPM_QUERY_LP_SETTINGS structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.
old-location: kernel\pep_ppm_query_lp_settings.htm
old-project: kernel
ms.assetid: 69A8792B-954E-49AF-A306-25B94183E58A
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: PEP_PPM_QUERY_LP_SETTINGS, PEP_PPM_QUERY_LP_SETTINGS, *PPEP_PPM_QUERY_LP_SETTINGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_PPM_QUERY_LP_SETTINGS
req.alt-loc: pep_x.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# PEP_PPM_QUERY_LP_SETTINGS structure



## -description
<p>The <b>PEP_PPM_QUERY_LP_SETTINGS</b> structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.</p>


## -syntax

````
typedef struct _PEP_PPM_QUERY_LP_SETTINGS {
  HANDLE RegistryRoot;
} PEP_PPM_QUERY_LP_SETTINGS, *PPEP_PPM_QUERY_LP_SETTINGS;
````


## -struct-fields
<dl>

### -field <b>RegistryRoot</b>

<dd>
<p>[out] The kernel handle to the registry root that contains the settings for a platform power scenario. For more information, see Remarks.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="kernel.pep_notify_ppm_query_lp_settings">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a> notification. The <b>RegistryRoot</b> member contains an output value that the PEP writes to the structure in response to this notification.</p>

<p>The PEP can provide settings for certain key power scenarios such as full-screen video playback and connected standby that have unique characteristics that can benefit from specially tuned power policies that are different from the default settings used by Windows. The PEP loads the settings for such a power scenario into the registry and passes the registry key for these settings to the operating system. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pep_x.h (include Pepfx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_notify_ppm_query_lp_settings">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_LP_SETTINGS structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
