---
UID: NS:ntifs._NETWORK_OPEN_ECP_CONTEXT_V0
title: "_NETWORK_OPEN_ECP_CONTEXT_V0"
author: windows-driver-content
description: The NETWORK_OPEN_ECP_CONTEXT_V0 structure is used to interpret network ECP contexts on files.
old-location: ifsk\network_open_ecp_context_v0.htm
old-project: ifsk
ms.assetid: 447d623a-88cb-4d3d-8b05-4f5624c707ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNETWORK_OPEN_ECP_CONTEXT_V0, ECP_Structures_8bd64f25-774a-4f87-a903-07ce0a3c0989.xml, NETWORK_OPEN_ECP_CONTEXT_V0, NETWORK_OPEN_ECP_CONTEXT_V0 structure [Installable File System Drivers], PNETWORK_OPEN_ECP_CONTEXT_V0, PNETWORK_OPEN_ECP_CONTEXT_V0 structure pointer [Installable File System Drivers], _NETWORK_OPEN_ECP_CONTEXT_V0, ifsk.network_open_ecp_context_v0, ntifs/NETWORK_OPEN_ECP_CONTEXT_V0, ntifs/PNETWORK_OPEN_ECP_CONTEXT_V0"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 7.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	NETWORK_OPEN_ECP_CONTEXT_V0
product: Windows
targetos: Windows
req.typenames: NETWORK_OPEN_ECP_CONTEXT_V0, *PNETWORK_OPEN_ECP_CONTEXT_V0
---

# _NETWORK_OPEN_ECP_CONTEXT_V0 structure
The NETWORK_OPEN_ECP_CONTEXT_V0 structure is used to interpret network ECP contexts on files.

## Syntax
````
typedef struct _NETWORK_OPEN_ECP_CONTEXT_V0 {
  USHORT Size;
  USHORT Reserved;
  struct {
    struct {
      NETWORK_OPEN_LOCATION_QUALIFIER  Location;
      NETWORK_OPEN_INTEGRITY_QUALIFIER Integrity;
    } in;
    struct {
      NETWORK_OPEN_LOCATION_QUALIFIER  Location;
      NETWORK_OPEN_INTEGRITY_QUALIFIER Integrity;
    } out;
  } DUMMYSTRUCTNAME;
} NETWORK_OPEN_ECP_CONTEXT_V0, *PNETWORK_OPEN_ECP_CONTEXT_V0;
````

## Members


`Size`

The size, in bytes, of this structure.

`Reserved`

Reserved. Must be set to zero.

`DUMMYSTRUCTNAME`

A structure that contains restrictions to apply for opening the file and to apply to the file after it is opened.

## Remarks
For information about how to use ECPs to associate extra information with a file when the file is created, see <a href="https://msdn.microsoft.com/e32aeec6-1a0a-4d21-8358-89d9fc0a15eb">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>. 

The NETWORK_OPEN_ECP_CONTEXT_V0 structure is read-only. You should use it to retrieve information about the network ECP context on a file only. For more information about this issue, see <a href="https://msdn.microsoft.com/6acb4be4-a7aa-431d-b2d8-3ef6d41cb4ef">System-Defined ECPs</a>.

If a caller must verify that the file system acknowledged the NETWORK_OPEN_ECP_CONTEXT_V0 context structure, the caller should call the <a href="..\fltkernel\nf-fltkernel-fltisecpacknowledged.md">FltIsEcpAcknowledged</a> or <a href="..\ntifs\nf-ntifs-fsrtlisecpacknowledged.md">FsRtlIsEcpAcknowledged</a> routine on the ECP after the operation is complete.

In most cases, drivers that run on Windows Vista and later versions of Windows use the <a href="..\ntifs\ns-ntifs-_network_open_ecp_context.md">NETWORK_OPEN_ECP_CONTEXT</a> structure to interpret network ECP contexts on files. However, drivers that run on Windows 7 and later versions of Windows and that must interpret network ECP contexts on files that reside on Windows Vista must use the NETWORK_OPEN_ECP_CONTEXT_V0 structure instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure is available starting with Windows 7. This structure is available starting with Windows 7. |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="..\ntifs\ne-ntifs-network_open_location_qualifier.md">NETWORK_OPEN_LOCATION_QUALIFIER</a>



<a href="..\ntifs\ns-ntifs-_network_open_ecp_context.md">NETWORK_OPEN_ECP_CONTEXT</a>



<a href="..\ntifs\ne-ntifs-network_open_integrity_qualifier.md">NETWORK_OPEN_INTEGRITY_QUALIFIER</a>