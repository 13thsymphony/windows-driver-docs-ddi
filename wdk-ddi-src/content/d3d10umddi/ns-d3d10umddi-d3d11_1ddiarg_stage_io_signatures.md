---
UID : NS:d3d10umddi.D3D11_1DDIARG_STAGE_IO_SIGNATURES
title : D3D11_1DDIARG_STAGE_IO_SIGNATURES
author : windows-driver-content
description : Describes an I/O signature.
old-location : display\d3d11_1ddiarg_stage_io_signatures.htm
old-project : display
ms.assetid : c7da4303-2ba4-4ac3-ad24-4ff25bb5466d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3d10umddi/D3D11_1DDIARG_STAGE_IO_SIGNATURES, D3D11_1DDIARG_STAGE_IO_SIGNATURES structure [Display Devices], D3D11_1DDIARG_STAGE_IO_SIGNATURES, display.d3d11_1ddiarg_stage_io_signatures
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3D11_1DDIARG_STAGE_IO_SIGNATURES
---

# D3D11_1DDIARG_STAGE_IO_SIGNATURES structure
Describes an I/O signature.

## Syntax
````
typedef struct D3D11_1DDIARG_STAGE_IO_SIGNATURES {
  D3D11_1DDIARG_SIGNATURE_ENTRY *pInputSignature;
  UINT                          NumInputSignatureEntries;
  D3D11_1DDIARG_SIGNATURE_ENTRY *pOutputSignature;
  UINT                          NumOutputSignatureEntries;
} D3D11_1DDIARG_STAGE_IO_SIGNATURES;
````

## Members


`NumInputSignatureEntries`

[in] The number of entries in the array that the <b>pInputSignature</b> member specifies.

`NumOutputSignatureEntries`

[in] The number of entries in the array that the <b>pOutputSignature</b> member specifies.

## Remarks
A signature is basically the union of all registers that are input and output by any shader that shares the signature. Therefore, a signature might be a superset of what a given shader might actually input or output. 

Hardware should determine that the upstream stage in the pipeline might provide some or all of the data in the signature that is laid out as the <b>pInputSignature</b> and <b>NumInputSignatureEntries</b> members specify. Similarly, hardware should determine that the downstream stage in the pipeline might consume some or all of the data in the signature that is laid out as the <b>pOutputSignature</b> and <b>NumOutputSignatureEntries</b> members specify.

To comply with the requirement for the event input and output registers to be reordered during shader compilation, the full signature is passed to the driver. Such reordering might depend on the driver being able to determine all of the registers in the signature, as well as which registers have system names (for example, names that the <b>SystemValue</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_signature_entry.md">D3D11_1DDIARG_SIGNATURE_ENTRY</a> structure specifies). Such reordering might also depend on the driver being able to determine registers that are not present in the current shader.

The declarations within the shader code itself also show which registers are actually used by a particular shader. These registers are possibly a subset of the input and output parts of the signature. If some hardware is not required to reorder input and output registers at compile time, the driver for that hardware can completely ignore the full signature that the <b>D3D11_1DDIARG_STAGE_IO_SIGNATURES</b> structure provides. The reference rasterizer, for example, does not require the information that the <b>D3D11_1DDIARG_STAGE_IO_SIGNATURES</b> structure provides.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_signature_entry.md">D3D11_1DDIARG_SIGNATURE_ENTRY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDIARG_STAGE_IO_SIGNATURES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>