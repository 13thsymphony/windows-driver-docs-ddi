---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE
title: PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure.
old-location: kernel\pep_acpi_initialize_extended_io_resource.htm
old-project: kernel
ms.assetid: 95464DE1-221A-4053-B124-4CFD44557CD3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE, PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_extended_io_resource, PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE
product: Windows
targetos: Windows
req.typenames: "*PPEP_WORK_TYPE, PEP_WORK_TYPE"
---


# PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function
The <b>PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a> structure.

## Syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE(
  _In_  BOOLEAN            ResourceUsage,
  _In_  UCHAR              Decode,
  _In_  BOOLEAN            IsMinFixed,
  _In_  BOOLEAN            IsMaxFixed,
  _In_  UCHAR              ISARanges,
  _In_  ULONGLONG          AddressGranularity,
  _In_  ULONGLONG          AddressMinimum,
  _In_  ULONGLONG          AddressMaximum,
  _In_  ULONGLONG          AddressTranslation,
  _In_  ULONGLONG          RangeLength,
  _In_  ULONGLONG          TypeSpecificAttributes,
  _In_  PUNICODE_STRING    DescriptorName,
  _In_  BOOLEAN            TranslationTypeNonStatic,
  _In_  BOOLEAN            TanslationSparseDensity,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````

## Parameters

`ResourceUsage`

This parameter is copied into the <b>GeneralFlags</b> member of the initialized <a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a> structure.

`Decode`

When set, indicates that this bridge subtractively decodes the address. This applies to top level bridges only. 

When not set, indicates that this bridge positively decodes this address.

`IsMinFixed`

When set, indicates that the minimum address is fixed.

`IsMaxFixed`

When set, indicates that the maximum address is fixed.

`ISARanges`

This parameter is copied into the <b>TypeSpecificFlags</b> member of the initialized <a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a> structure.

`AddressGranularity`

A bit mask indicating which bits have been decoded.

`AddressMinimum`

For bridges that translate addresses, this indicates the minimum starting address on the secondary side of the bridge.

`AddressMaximum`

For bridges that translate addresses, this indicates the maximum starting address on the secondary side of the bridge.

`AddressTranslation`

For bridges that translate addresses across the bridge, this is the
address on the primary side.

`RangeLength`

The length of the address range.

`TypeSpecificAttributes`

The type-specific attributes for this resource.

`DescriptorName`

The name of the resource descriptor.

`TranslationTypeNonStatic`

When true, indicates that the resource uses type translation. Otherwise, it uses type-static translation.

`TanslationSparseDensity`

When false, indicates that this is a dense translation. Otherwise, it is sparse.

`Resource`

This is cast to *<a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | pepfx.h |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>