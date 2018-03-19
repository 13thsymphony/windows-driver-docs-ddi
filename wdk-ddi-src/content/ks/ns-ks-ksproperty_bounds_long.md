---
UID: NS:ks.KSPROPERTY_BOUNDS_LONG
title: KSPROPERTY_BOUNDS_LONG
author: windows-driver-content
description: The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.
old-location: stream\ksproperty_bounds_long.htm
old-project: stream
ms.assetid: 16804ff1-8531-48aa-baf6-b89ccfe25d07
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG union [Streaming Media Devices], PKSPROPERTY_BOUNDS_LONG, PKSPROPERTY_BOUNDS_LONG union pointer [Streaming Media Devices], ks-struct_805e1a44-91bb-45be-a99d-174e98639d9e.xml, ks/KSPROPERTY_BOUNDS_LONG, ks/PKSPROPERTY_BOUNDS_LONG, stream.ksproperty_bounds_long"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSPROPERTY_BOUNDS_LONG
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG
---

# KSPROPERTY_BOUNDS_LONG structure
The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.

## Syntax
````
typedef union {
  struct {
    LONG SignedMinimum;
    LONG SignedMaximum;
  };
  struct {
    ULONG UnsignedMinimum;
    ULONG UnsignedMaximum;
  };
} KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG;
````

## Members


`_SIGNED`



`_UNSIGNED`



## Remarks
This structure specifies a range of 32-bit values for a property. Use only when the <b>MembersFlags</b> member of the relevant <a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a> is set to KSPROPERTY_MEMBER_RANGES. Use this structure in the <b>Members</b> array in the relevant <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structure.

See the Testcap sample in the Windows Driver Kit (WDK) for examples of usage.

Also see related information in <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a>



<a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a>



<a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a>