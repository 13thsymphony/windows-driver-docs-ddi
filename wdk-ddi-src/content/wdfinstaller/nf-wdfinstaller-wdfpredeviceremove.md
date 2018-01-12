---
UID: NF:wdfinstaller.WdfPreDeviceRemove
title: WdfPreDeviceRemove function
author: windows-driver-content
description: The co-installer's WdfPreDeviceRemove function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer deletes the driver's kernel-mode service.
old-location: wdf\wdfpredeviceremove.htm
old-project: wdf
ms.assetid: 8cde623d-a255-45ff-ab1e-bdd0c14a02a0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfPreDeviceRemove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfPreDeviceRemove
req.alt-loc: N/A,N/A.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll: 
req.irql: 
req.typenames: *PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WdfPreDeviceRemove function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The co-installer's <b>WdfPreDeviceRemove</b> function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer deletes the driver's kernel-mode service. 



## -syntax

````
ULONG WdfPreDeviceRemove(
  _In_     LPCWSTR InfPath,
  _In_opt_ LPCWSTR InfSectionName
);
````


## -parameters

### -param InfPath [in]

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <a href="https://msdn.microsoft.com/1fbe6289-2ca8-4ca8-b004-ecf513f9b0bd">GetCurrentDirectory</a>, which is described in the Microsoft Windows SDK.


### -param InfSectionName [in, optional]

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="wdf.installing_the_framework_s_co_installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


## -returns
<b>WdfPreDeviceRemove</b> returns <b>ERROR_SUCCESS</b> if the operation succeeds. Otherwise, the function returns one of the additional <b>ERROR_XXX</b> values that are defined in Winerror.h.


## -remarks
The installer for the framework-based drivers of a non-PnP device must call <b>WdfPreDeviceRemove</b> before the installer calls <a href="https://msdn.microsoft.com/5b0fc714-60e0-4ae3-8fa8-ace36dab2fb0">DeleteService</a>.

To obtain the address of the co-installer's <b>WdfPreDeviceRemove</b> function, the installer must call <a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a> after the installer has called <a href="https://msdn.microsoft.com/d936b4dd-058c-48e1-834b-b47ef6d8ef65">LoadLibrary</a> to load the co-installer.

For more information about the <b>WdfPreDeviceRemove</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://msdn.microsoft.com/99676d85-feb2-482c-a91b-cfc48be5904c">Installing a Non-PnP Driver</a>. For more information about <a href="https://msdn.microsoft.com/5b0fc714-60e0-4ae3-8fa8-ace36dab2fb0">DeleteService</a>, <a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a>, and <a href="https://msdn.microsoft.com/d936b4dd-058c-48e1-834b-b47ef6d8ef65">LoadLibrary</a>, see the Microsoft Windows SDK documentation.

For a code example that uses the <b>WdfPreDeviceRemove</b> function, see the installer for the <a href="wdf.sample_kmdf_drivers">NONPNP</a> sample.


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
<dt>Wdfinstaller.h (include Wdfinstaller.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see <a href="wdf.installing_the_framework_s_co_installer">Using the KMDF Co-installer</a>.)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfinstaller\nf-wdfinstaller-wdfpostdeviceremove.md">WdfPostDeviceRemove</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPreDeviceRemove function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

