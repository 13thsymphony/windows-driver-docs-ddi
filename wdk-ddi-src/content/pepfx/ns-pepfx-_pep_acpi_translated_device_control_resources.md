---
UID : NS:pepfx._PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
title : "_PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES"
author : windows-driver-content
description : The PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use.
old-location : kernel\pep_acpi_translated_device_control_resources.htm
old-project : kernel
ms.assetid : 1274EF11-6A0D-4464-992D-4E27C981971F
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : "_PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, pepfx/PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, kernel.pep_acpi_translated_device_control_resources, *PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure [Kernel-Mode Driver Architecture]"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES"
---

# _PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure
The <b>PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</b> structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use.

## Syntax
````
struct PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES {
  PEPHANDLE        DeviceHandle;
  ULONG            RequestFlags;
  NTSTATUS         Status;
  SIZE_T           ResourceBufferSize;
  CM_RESOURCE_LIST TranslatedResources;
};
````

## Members


`DeviceHandle`

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.

`RequestFlags`

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_TDCR_FLAG_NONE (0x0).

`Status`

[out] An NTSTATUS value that indicates the status of the resource translation. The PEP sets this member to STATUS_SUCCESS to indicate that the PEP successfully received the translated resources. Otherwise, the PEP sets this member to an appropriate error status code.

`TranslatedResources`

[in] A <a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure that serves as the header for the resource list. The remainder of the resource list immediately follows this header.

`TranslatedResourcesSize`



## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186698">PEP_NOTIFY_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</a> notification to provide the PEP with a list of translated power control resources. The <b>RequestFlags</b>, <b>ResourceBufferSize</b>, and <b>TranslatedResources</b> members of the structure contain input values that the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) supplies when this notification is sent. The <b>Status</b> member contains an output value that the PEP writes to the structure in response to the notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186698">PEP_NOTIFY_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</a>

<a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>