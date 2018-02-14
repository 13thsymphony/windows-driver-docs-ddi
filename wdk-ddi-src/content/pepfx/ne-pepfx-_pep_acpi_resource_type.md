---
UID: NE:pepfx._PEP_ACPI_RESOURCE_TYPE
title: "_PEP_ACPI_RESOURCE_TYPE"
author: windows-driver-content
description: The PEP_ACPI_RESOURCE_TYPE enumeration is used to identify the type of ACPI resource that is contained in the PEP_ACPI_RESOURCE union.
old-location: kernel\pep_acpi_resource_type.htm
old-project: kernel
ms.assetid: C67FA5DF-D2E4-4F00-B22F-9218F0012708
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_ACPI_RESOURCE_TYPE enumeration [Kernel-Mode Driver Architecture], pepfx/PepAcpiExtendedMemory, kernel.pep_acpi_resource_type, pepfx/PepAcpiGpioInt, PepAcpiInterrupt, PepAcpiExtendedMemory, PepAcpiIoPort, pepfx/PepAcpiIoPort, pepfx/PepAcpiGpioIo, pepfx/PepAcpiMemory, PEP_ACPI_RESOURCE_TYPE, PepAcpiSpbSpi, PepAcpiGpioInt, PepAcpiMemory, pepfx/PEP_ACPI_RESOURCE_TYPE, _PEP_ACPI_RESOURCE_TYPE, PepAcpiGpioIo, pepfx/PepAcpiInterrupt, pepfx/PepAcpiSpbSpi, pepfx/PepAcpiSpbI2c, PepAcpiExtendedIo, PepAcpiSpbUart, pepfx/PepAcpiExtendedIo, pepfx/PepAcpiSpbUart, PepAcpiSpbI2c
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_RESOURCE_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_RESOURCE_TYPE
---

# _PEP_ACPI_RESOURCE_TYPE Enumeration
The <b>PEP_ACPI_RESOURCE_TYPE</b> enumeration is used to identify the type of ACPI resource that is contained in the <a href="..\pepfx\ns-pepfx-_pep_acpi_resource.md">PEP_ACPI_RESOURCE</a> union.

## Syntax
````
typedef enum _PEP_ACPI_RESOURCE_TYPE { 
  PepAcpiMemory,
  PepAcpiIoPort,
  PepAcpiInterrupt,
  PepAcpiGpioIo,
  PepAcpiGpioInt,
  PepAcpiSpbI2c,
  PepAcpiSpbSpi,
  PepAcpiSpbUart,
  PepAcpiExtendedMemory,
  PepAcpiExtendedIo
} PEP_ACPI_RESOURCE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PepAcpiExtendedIo</td>
                    <td>Indicates that the resource is an ACPI extended IO resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiExtendedMemory</td>
                    <td>Indicates that the resource is an ACPI extended memory resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiGpioInt</td>
                    <td>Indicates that the resource is an ACPI GPIO interrupt resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiGpioIo</td>
                    <td>Indicates that the resource is an ACPI GPIO resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiInterrupt</td>
                    <td>Indicates that the resource is an ACPI interrupt resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiIoPort</td>
                    <td>Indicates that the resource is an ACPI IO port resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiMemory</td>
                    <td>Indicates that the resource is an ACPI memory resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiSpbI2c</td>
                    <td>Indicates that the resource is an ACPI I2C serial bus resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiSpbSpi</td>
                    <td>Indicates that the resource is an ACPI SPI serial bus resource.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiSpbUart</td>
                    <td>Indicates that the resource is an ACPI UART serial bus resource.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h |

    ## See Also

        <a href="..\pepfx\ns-pepfx-_pep_acpi_resource.md">PEP_ACPI_RESOURCE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_request_convert_to_bios_resources.md">PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_RESOURCE_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>