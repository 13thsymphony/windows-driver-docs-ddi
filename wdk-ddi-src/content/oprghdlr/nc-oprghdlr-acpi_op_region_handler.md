---
UID: NC:oprghdlr.ACPI_OP_REGION_HANDLER
title: ACPI_OP_REGION_HANDLER
author: windows-driver-content
description: An ACPI_OP_REGION_HANDLER-typed routine is supplied by an ACPI device function driver to provide access by the ACPI driver to the device's operation region.
old-location: acpi\pacpi_op_region_handler.htm
old-project: acpi
ms.assetid: c3a5af59-c97c-42be-bc43-afa30ad710ec
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ACPI_OP_REGION_HANDLER, AcpiOpRegionHandler, AcpiOpRegionHandler callback function [ACPI Devices], acpi.pacpi_op_region_handler, opregref_be7bf2cd-0369-4efd-bbdb-5ad7dc28c33d.xml, oprghdlr/AcpiOpRegionHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: oprghdlr.h
req.include-header: Oprghdlr.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: "(See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	oprghdlr.h
api_name:
-	AcpiOpRegionHandler
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---


# ACPI_OP_REGION_HANDLER callback function
An ACPI_OP_REGION_HANDLER-typed routine is supplied by an ACPI device function driver to provide access by the <a href="https://msdn.microsoft.com/38ca54e0-defe-48b2-ab00-a5f688c2eb01">ACPI driver</a> to the device's operation region.

## Syntax

```
ACPI_OP_REGION_HANDLER AcpiOpRegionHandler;

NTSTATUS AcpiOpRegionHandler(
  ULONG AccessType,
  PVOID OperationRegionObject,
  ULONG Address,
  ULONG Size,
  PULONG Data,
  ULONG_PTR Context,
  PACPI_OP_REGION_CALLBACK CompletionHandler,
  PVOID CompletionContext
)
{...}
```

## Parameters

`AccessType`

Specifies one of the following access types.

<table>
<tr>
<th>Access Type</th>
<th>Description</th>
</tr>
<tr>
<td>
ACPI_OPREGION_WRITE 

</td>
<td>
Write to the operation region memory buffer.

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_READ

</td>
<td>
Read from the operation region memory buffer.

</td>
</tr>
</table>

`OperationRegionObject`

Specifies the operation region object returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff536158">RegisterOpRegionHandler</a> for the operation region handler.

`Address`

Specifies a byte offset in the operation region memory buffer. Depending on the access type, data is transferred to or from this memory location.

`Size`

Specifies the number of bytes to access.

`Data`

Pointer to the data buffer supplied by the ACPI driver that is associated with the access. For a read access, bytes are transferred from the operation region memory buffer to the data buffer. For a write access, bytes are transferred from the data buffer to the operation region memory buffer.

`Context`

Pointer to the same operation region context that the function driver specified when it registered the operation region handler.

`CompletionHandler`

Reserved for internal use.

`CompletionContext`

Reserved for internal use.


## Return Value

Returns one of the following status values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The access was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The access type is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_Xxx</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred.

</td>
</tr>
</table>

## Remarks

When the ACPI driver calls an operation region handler, it specifies values for <i>Address</i> and <i>Size</i> that ensure that the access is within the operation region that is defined in the ACPI BIOS for the ACPI device. The ACPI device function driver must ensure that the operation region memory buffer it allocates is at least as large, in bytes, as the operation region defined for the ACPI device.

For more information about operation region handlers, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/supporting-an-operation-region">Supporting an Operation Region</a>.

An ACPI_OP_REGION_HANDLER-typed routine runs at the caller's IRQL.

For detailed information about constraints on operation regions, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=57185">Advanced Configuration and Power Interface (ACPI) Specification</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | oprghdlr.h (include Oprghdlr.h) |
| **IRQL** | "(See Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536135">DeRegisterOpRegionHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536158">RegisterOpRegionHandler</a>