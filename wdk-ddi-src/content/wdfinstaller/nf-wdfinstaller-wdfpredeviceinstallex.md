---
UID: NF:wdfinstaller.WdfPreDeviceInstallEx
title: WdfPreDeviceInstallEx function
author: windows-driver-content
description: The co-installer's WdfPreDeviceInstallEx function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service.
old-location: wdf\wdfpredeviceinstallex.htm
old-project: wdf
ms.assetid: 99de930a-0d01-4177-b0d9-4692cc570303
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfPreDeviceInstallEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.alt-api: WdfPreDeviceInstallEx
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

# WdfPreDeviceInstallEx function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The co-installer's <b>WdfPreDeviceInstallEx</b> function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service. 



## -syntax

````
ULONG WdfPreDeviceInstallEx(
  _In_     LPCWSTR                          InfPath,
  _In_opt_ LPCWSTR                          InfSectionName,
  _In_     PWDF_COINSTALLER_INSTALL_OPTIONS ClientOptions
);
````


## -parameters

### -param InfPath [in]

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <b>GetCurrentDirectory</b>, which is described in the Microsoft Windows SDK.


### -param InfSectionName [in, optional]

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="wdf.installing_the_framework_s_co_installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


### -param ClientOptions [in]

A pointer to a caller-allocated <a href="..\wdfinstaller\ns-wdfinstaller-_wdf_coinstaller_install_options.md">WDF_COINSTALLER_INSTALL_OPTIONS</a>-typed structure that contains driver-specified installation options. 


## -returns
<b>WdfPreDeviceInstallEx</b> returns ERROR_SUCCESS if the operation succeeds. Otherwise, the function returns one of the additional ERROR_<i>XXX</i> values that are defined in <i>Winerror.h</i>.


## -remarks
The installer for the framework-based drivers of a non-PnP device must call <a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstall.md">WdfPreDeviceInstall</a> or <b>WdfPreDeviceInstallEx</b> before the installer calls <b>CreateService</b>.

To obtain the address of the co-installer's <b>WdfPreDeviceInstallEx</b> function, the installer must call <b>GetProcAddress</b> after the installer has called <b>LoadLibrary</b> to load the co-installer.

If the co-installer determines that the computer must be restarted to complete the driver installation (typically because an older version of the framework was previously installed), the <b>WdfPreDeviceInstallEx</b> function enables you to control when or whether the user is prompted to restart the computer, as follows:

If the installer sets the <i>ShowRebootPrompt</i> member of the <a href="..\wdfinstaller\ns-wdfinstaller-_wdf_coinstaller_install_options.md">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure to <b>TRUE</b>, <b>WdfPreDeviceInstallEx</b> informs the PnP manager that the computer must be restarted, and the PnP manager prompts the user that a restart is necessary. Setting the <i>ShowRebootPrompt</i> member to <b>TRUE</b> is equivalent to calling <a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstall.md">WdfPreDeviceInstall</a>.

If the installer sets the <i>ShowRebootPrompt</i> member of the <a href="..\wdfinstaller\ns-wdfinstaller-_wdf_coinstaller_install_options.md">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure to <b>FALSE</b>, <b>WdfPreDeviceInstallEx</b> does not inform the PnP manager that a restart is necessary. Instead, the function returns <b>ERROR_SUCCESS_REBOOT_REQUIRED</b>. Your installer can determine when or whether to restart the computer, 

For more information about the <b>WdfPreDeviceInstallEx</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://msdn.microsoft.com/99676d85-feb2-482c-a91b-cfc48be5904c">Installing a Non-PnP Driver</a>. For more information about <b>CreateService</b>, <b>GetProcAddress</b>, and <b>LoadLibrary</b>, see the Microsoft Windows SDK documentation.

For a code example that uses the <b>WdfPreDeviceInstallEx</b> function, see the installer for the <a href="wdf.sample_kmdf_drivers">NONPNP</a> sample.


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
1.9

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
<a href="..\wdfinstaller\nf-wdfinstaller-wdfpostdeviceinstall.md">WdfPostDeviceInstall</a>
</dt>
<dt>
<a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstall.md">WdfPreDeviceInstall</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPreDeviceInstallEx function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

