---
UID : NE:wdfdevice._WDF_SPECIAL_FILE_TYPE
title : _WDF_SPECIAL_FILE_TYPE
author : windows-driver-content
description : The WDF_SPECIAL_FILE_TYPE enumeration identifies special file types that a device can support.
old-location : wdf\wdf_special_file_type.htm
old-project : wdf
ms.assetid : 3879570f-e083-4eaf-aa5b-9b78d8f826c1
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_SPECIAL_FILE_TYPE, WDF_SPECIAL_FILE_TYPE, *PWDF_SPECIAL_FILE_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WDF_SPECIAL_FILE_TYPE
req.alt-loc : wdfdevice.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section.
req.typenames : WDF_SPECIAL_FILE_TYPE, *PWDF_SPECIAL_FILE_TYPE
req.product : Windows 10 or later.
---

# _WDF_SPECIAL_FILE_TYPE Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_SPECIAL_FILE_TYPE</b> enumeration identifies special file types that a device can support.

## Syntax
````
typedef enum _WDF_SPECIAL_FILE_TYPE { 
  WdfSpecialFileUndefined    = 0,
  WdfSpecialFilePaging       = 1,
  WdfSpecialFileHibernation  = 2,
  WdfSpecialFileDump         = 3,
  WdfSpecialFileBoot         = 4,
  WdfSpecialFileMax          = 5
} WDF_SPECIAL_FILE_TYPE, *PWDF_SPECIAL_FILE_TYPE;
````

## Constants

<table>

<tr>
<td>WdfSpecialFileBoot</td>
<td>The device supports boot files. This constant is available in version 1.11 and later versions of KMDF.</td>
</tr>

<tr>
<td>WdfSpecialFileDump</td>
<td>The device supports dump files.</td>
</tr>

<tr>
<td>WdfSpecialFileHibernation</td>
<td>The device supports hibernation files.</td>
</tr>

<tr>
<td>WdfSpecialFileMax</td>
<td>For internal use only.</td>
</tr>

<tr>
<td>WdfSpecialFilePaging</td>
<td>The device supports paging files.</td>
</tr>

<tr>
<td>WdfSpecialFileUndefined</td>
<td>For internal use only.</td>
</tr>
</table>

## Remarks

For more information, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetspecialfilesupport.md">WdfDeviceSetSpecialFileSupport</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_SPECIAL_FILE_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>