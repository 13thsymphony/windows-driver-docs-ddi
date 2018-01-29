---
UID : NF:wdfinstaller.WdfPostDeviceRemove
title : WdfPostDeviceRemove function
author : windows-driver-content
description : The co-installer's WdfPostDeviceRemove function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has deleted the driver's kernel-mode service.
old-location : wdf\wdfpostdeviceremove.htm
old-project : wdf
ms.assetid : f29579de-ba5d-4b7a-9aeb-558be03d7eef
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfPostDeviceRemove function, kmdf.wdfpostdeviceremove, wdfinstaller/WdfPostDeviceRemove, wdf.wdfpostdeviceremove, DFCoinstallerRef_82480a49-b7ac-4e1d-b942-93d1eb8a5c34.xml, WdfPostDeviceRemove, PFN_WDFPOSTDEVICEREMOVE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfinstaller.h
req.include-header : Wdfinstaller.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS"
req.product : Windows 10 or later.
---


# WdfPostDeviceRemove function
<p class="CCE_Message">[Applies to KMDF only]

The co-installer's <b>WdfPostDeviceRemove</b> function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has deleted the driver's kernel-mode service.

## Syntax

````
ULONG WdfPostDeviceRemove(
  _In_     LPCWSTR InfPath,
  _In_opt_ LPCWSTR InfSectionName
);
````

## Parameters

`InfPath`

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <b>GetCurrentDirectory</b>, which is described in the Microsoft Windows SDK.

`InfSectionName`

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/installing-the-framework-s-co-installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


## Return Value

<b>WdfPostDeviceRemove</b> returns ERROR_SUCCESS if the operation succeeds. Otherwise, the function returns one of the additional ERROR_<i>XXX</i> values that are defined in <i>Winerror.h</i>.

## Remarks

The installer for the framework-based drivers of a non-PnP device must call <b>WdfPostDeviceRemove</b> after the installer calls <b>DeleteService</b>.

To obtain the address of the co-installer's <b>WdfPostDeviceRemove</b> function, the installer must call <b>GetProcAddress</b> after the installer has called <b>LoadLibrary</b> to load the co-installer.

For more information about the <b>WdfPostDeviceRemove</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://msdn.microsoft.com/99676d85-feb2-482c-a91b-cfc48be5904c">Installing a Non-PnP Driver</a>. For more information about <b>DeleteService</b>, <b>GetProcAddress</b>, and <b>LoadLibrary</b>, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfinstaller.h (include Wdfinstaller.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceremove.md">WdfPreDeviceRemove</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPostDeviceRemove function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>