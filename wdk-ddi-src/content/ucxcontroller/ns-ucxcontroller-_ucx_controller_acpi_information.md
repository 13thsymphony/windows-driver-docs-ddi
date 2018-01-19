---
UID : NS:ucxcontroller._UCX_CONTROLLER_ACPI_INFORMATION
title : _UCX_CONTROLLER_ACPI_INFORMATION
author : windows-driver-content
description : This structure provides information about an advanced Configuration and power interface (ACPI) USB controller.
old-location : buses\_ucx_controller_acpi_information.htm
old-project : usbref
ms.assetid : BB5C69FF-166A-4A38-BF5E-FD644FCD1285
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _UCX_CONTROLLER_ACPI_INFORMATION, *PUCX_CONTROLLER_ACPI_INFORMATION, UCX_CONTROLLER_ACPI_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ucxcontroller.h
req.include-header : Ucxclass.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UCX_CONTROLLER_ACPI_INFORMATION
req.alt-loc : Ucxcontroller.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PUCX_CONTROLLER_ACPI_INFORMATION, UCX_CONTROLLER_ACPI_INFORMATION"
req.product : Windows 10 or later.
---

# _UCX_CONTROLLER_ACPI_INFORMATION structure
This structure provides information about an advanced Configuration and power interface (ACPI) USB controller.

## Syntax
````
typedef struct _UCX_CONTROLLER_ACPI_INFORMATION {
  CHAR VendorId[MAX_VENDOR_ID_STRING_LENGTH];
  CHAR DeviceId[MAX_DEVICE_ID_STRING_LENGTH];
  CHAR RevisionId[MAX_REVISION_ID_STRING_LENGTH];
} UCX_CONTROLLER_ACPI_INFORMATION, *P_UCX_CONTROLLER_ACPI_INFORMATION;
````

## Members

        
            `DeviceId`

            The device ID of the ACPI USB controller.
        
            `RevisionId`

            The revision ID of the ACPI USB controller.
        
            `VendorId`

            The vendor ID of the ACPI USB controller.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ucxcontroller.h (include Ucxclass.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a>
</dt>
<dt>
<a href="..\ucxcontroller\nf-ucxcontroller-ucx_controller_config_set_acpi_info.md">UCX_CONTROLLER_CONFIG_SET_ACPI_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_CONTROLLER_ACPI_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>