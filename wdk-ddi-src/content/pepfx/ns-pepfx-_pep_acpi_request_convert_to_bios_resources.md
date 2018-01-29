---
UID : NS:pepfx._PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
title : _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
author : windows-driver-content
description : The PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure is used in the process of converting ACPI resources to BIOS resources by one of the PEP initialization functions.
old-location : kernel\pep_acpi_request_convert_to_bios_resources.htm
old-project : kernel
ms.assetid : DF9FD748-88E8-4E32-B698-0E8A3BE319DB
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure [Kernel-Mode Driver Architecture], PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, *PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, kernel.pep_acpi_request_convert_to_bios_resources, PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure pointer [Kernel-Mode Driver Architecture], pepfx/PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, pepfx/PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
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
req.typenames : PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, *PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
---

# _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure
The <b>PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES</b> structure is used in the process of converting ACPI resources to BIOS resources by one of the <a href="https://msdn.microsoft.com/1FBF406C-22C7-4D46-840C-9966C3515B63">PEP initialization functions</a>.

## Syntax
````
typedef struct _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES {
  NTSTATUS           TranslationStatus;
  PPEP_ACPI_RESOURCE InputBuffer;
  SIZE_T             InputBufferSize;
  PVOID              OutputBuffer;
  SIZE_T             OutputBufferSize;
  ULONG              Flags;
} PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, *PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES;
````

## Members


`Flags`

The value contained in the <a href="..\pepfx\ns-pepfx-_pep_acpi_resource_flags.md">PEP_ACPI_RESOURCE_FLAGS</a> structure.

`InputBuffer`

A pointer to a <a href="..\pepfx\ns-pepfx-_pep_acpi_resource.md">PEP_ACPI_RESOURCE</a> containing the input buffer.

`InputBufferSize`

The size of the input buffer.

`OutputBuffer`

A pointer to the output buffer containing the translated structure.

`OutputBufferSize`

The size of the output buffer.

`TranslationStatus`

The result code from the resource translation call.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_resource_flags.md">PEP_ACPI_RESOURCE_FLAGS</a>

<a href="..\pepfx\ns-pepfx-_pep_acpi_resource.md">PEP_ACPI_RESOURCE</a>

<a href="https://msdn.microsoft.com/1FBF406C-22C7-4D46-840C-9966C3515B63">PEP initialization functions</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>