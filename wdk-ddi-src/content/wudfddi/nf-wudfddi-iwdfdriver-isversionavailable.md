---
UID: NF.wudfddi.IWDFDriver.IsVersionAvailable
title: IWDFDriver::IsVersionAvailable method
author: windows-driver-content
description: The IsVersionAvailable method determines whether the specified version of the framework is available.
old-location: wdf\iwdfdriver_isversionavailable.htm
old-project: wdf
ms.assetid: 9048a568-3369-44eb-8fa8-361ce968a253
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFDriver, IWDFDriver::IsVersionAvailable, IsVersionAvailable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFDriver.IsVersionAvailable
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.product: Windows 10 or later.
---

# IWDFDriver::IsVersionAvailable method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsVersionAvailable</b> method determines whether the specified version of the framework is available.



## -syntax

````
BOOL IsVersionAvailable(
  [in] UMDF_VERSION_DATA *pMinimumVersion
);
````


## -parameters

### -param pMinimumVersion [in]

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-umdf_version_data.md">UMDF_VERSION_DATA</a> structure that describes the minimum version of the framework that the driver supports.


## -returns
<b>IsVersionAvailable</b> returns a BOOL value that indicates whether the given version of the framework is available. <b>TRUE</b> indicates the version of the framework is available. <b>FALSE</b> indicates the version of the framework is not available.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>
</dt>
<dt>
<a href="..\wudfddi_types\ns-wudfddi_types-umdf_version_data.md">UMDF_VERSION_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDriver::IsVersionAvailable method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

