---
UID: NS.WUDFDDI_TYPES.UMDF_VERSION_DATA
title: UMDF_VERSION_DATA
author: windows-driver-content
description: The UMDF_VERSION_DATA structure describes a version of the framework.
old-location: wdf\umdf_version_data.htm
old-project: wdf
ms.assetid: b83a786d-0b17-4129-bdd4-86942ad9d3ec
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: UMDF_VERSION_DATA, *PUMDF_VERSION_DATA, UMDF_VERSION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfddi_types.h
req.include-header: Wudfddi_types.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UMDF_VERSION_DATA
req.alt-loc: Wudfddi_types.h
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

# UMDF_VERSION_DATA structure



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]
The <b>UMDF_VERSION_DATA</b> structure describes a version of the framework.


## -syntax

````
typedef struct UMDF_VERSION_DATA {
  ULONG MajorNumber;
  ULONG MinorNumber;
  ULONG ServiceNumber;
} UMDF_VERSION_DATA, *PUMDF_VERSION_DATA;
````


## -struct-fields

### -field MajorNumber

A number that specifies the major version of the framework. 

### -field MinorNumber

A number that specifies the minor version of the framework. 

### -field ServiceNumber

A number that specifies the service of the framework. 

## -remarks
A UMDF driver supplies a pointer to a <b>UMDF_VERSION_DATA</b> structure to the <a href="wdf.iwdfdriver_isversionavailable">IWDFDriver::IsVersionAvailable</a> method to describe the minimum version of the framework that the driver supports.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh780327">Microsoft_WDF_UMDF_Version</a> is a global variable of type  <b>UMDF_VERSION_DATA</b> that specifies the major version, minor version, and service number for the current release of the framework.
      

For example, in Windows 8, Wudfddi.h specifies: <div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UMDF_VERSION_DATA Microsoft_WDF_UMDF_Version = {1, 11,  0}</pre>
</td>
</tr>
</table></span></div>


When you compile a driver using Wudfddi.h, <a href="https://msdn.microsoft.com/library/windows/hardware/hh780327">Microsoft_WDF_UMDF_Version</a> is included in the driver binary and exported using <a href="https://msdn.microsoft.com/en-us/library/a90k134d">__declspec(dllexport)</a>.

 When the system loads your driver, the host process (WUDFHost.exe) verifies  that the driver's major version matches the framework's major version and that the driver's minor version is less than or equal to the framework's minor version.

  The driver does not need to take any action to provide this version number to the framework, other than building with Wudfddi.h.

End of support:
 Unavailable in UMDF 2.0 and later.

Minimum UMDF version:
 1.0

Header:
 Wudfddi.h (include Wudfddi.h) 

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wudfddi_types.h (include Wudfddi_types.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.iwdfdriver_isversionavailable">IWDFDriver::IsVersionAvailable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh780327">Microsoft_WDF_UMDF_Version</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20UMDF_VERSION_DATA structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
