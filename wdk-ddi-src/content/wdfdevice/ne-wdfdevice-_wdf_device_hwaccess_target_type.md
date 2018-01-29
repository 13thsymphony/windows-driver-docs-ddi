---
UID : NE:wdfdevice._WDF_DEVICE_HWACCESS_TARGET_TYPE
title : _WDF_DEVICE_HWACCESS_TARGET_TYPE
author : windows-driver-content
description : The WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration is used internally by the framework. Do not use.
old-location : wdf\wdf_device_hwaccess_target_type.htm
old-project : wdf
ms.assetid : AF462D58-1854-4A56-8DC6-63F373439842
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfdevice/WdfDeviceHwAccessTargetTypeRegister, WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration, wdfdevice/WdfDeviceHwAccessTargetTypeRegisterBuffer, wdf.wdf_device_hwaccess_target_type, wudfddi_types/WdfDeviceHwAccessTargetTypePortBuffer, umdf.wdf_device_hwaccess_target_type, WDF_DEVICE_HWACCESS_TARGET_TYPE, wdfdevice/WdfDeviceHwAccessTargetTypeMaximum, wudfddi_types/WdfDeviceHwAccessTargetTypeRegister, PWDF_DEVICE_HWACCESS_TARGET_TYPE, wdfdevice/WdfDeviceHwAccessTargetTypePort, _WDF_DEVICE_HWACCESS_TARGET_TYPE, WdfDeviceHwAccessTargetTypePort, WdfDeviceHwAccessTargetTypeMaximum, PWDF_DEVICE_HWACCESS_TARGET_TYPE enumeration pointer, *PWDF_DEVICE_HWACCESS_TARGET_TYPE, wdfdevice/WDF_DEVICE_HWACCESS_TARGET_TYPE, WdfDeviceHwAccessTargetTypeRegisterBuffer, WdfDeviceHwAccessTargetTypeRegister, wdfdevice/WdfDeviceHwAccessTargetTypePortBuffer, wdfdevice/WdfDeviceHwAccessTargetTypeInvalid, WdfDeviceHwAccessTargetTypeInvalid, wudfddi_types/WdfDeviceHwAccessTargetTypeMaximum, wudfddi_types/WDF_DEVICE_HWACCESS_TARGET_TYPE, wudfddi_types/WdfDeviceHwAccessTargetTypePort, wudfddi_types/WdfDeviceHwAccessTargetTypeRegisterBuffer, wdfdevice/PWDF_DEVICE_HWACCESS_TARGET_TYPE, wudfddi_types/PWDF_DEVICE_HWACCESS_TARGET_TYPE, WdfDeviceHwAccessTargetTypePortBuffer, wudfddi_types/WdfDeviceHwAccessTargetTypeInvalid
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_DEVICE_HWACCESS_TARGET_TYPE, *PWDF_DEVICE_HWACCESS_TARGET_TYPE
req.product : Windows 10 or later.
---

# _WDF_DEVICE_HWACCESS_TARGET_TYPE Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_DEVICE_HWACCESS_TARGET_TYPE</b> enumeration is used internally by the framework. Do not use.

## Syntax
````
typedef enum __WDF_IO_TARGET_STATE { 
  WdfDeviceHwAccessTargetTypeInvalid         = 0,
  WdfDeviceHwAccessTargetTypeRegister        = 1,
  WdfDeviceHwAccessTargetTypeRegisterBuffer  = 2,
  WdfDeviceHwAccessTargetTypePort            = 3,
  WdfDeviceHwAccessTargetTypePortBuffer      = 4,
  WdfDeviceHwAccessTargetTypeMaximum         = 5
} WDF_DEVICE_HWACCESS_TARGET_TYPE, *PWDF_DEVICE_HWACCESS_TARGET_TYPE;
````

## Constants

<table>

<tr>
<td>WdfDeviceHwAccessTargetTypeInvalid</td>
<td></td>
</tr>

<tr>
<td>WdfDeviceHwAccessTargetTypeMaximum</td>
<td></td>
</tr>

<tr>
<td>WdfDeviceHwAccessTargetTypePort</td>
<td></td>
</tr>

<tr>
<td>WdfDeviceHwAccessTargetTypePortBuffer</td>
<td></td>
</tr>

<tr>
<td>WdfDeviceHwAccessTargetTypeRegister</td>
<td></td>
</tr>

<tr>
<td>WdfDeviceHwAccessTargetTypeRegisterBuffer</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.11 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561319">UMDF Structures and Enumeration Types</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>