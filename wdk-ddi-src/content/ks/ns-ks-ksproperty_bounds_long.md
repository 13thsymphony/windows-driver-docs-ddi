---
UID : NS:ks.KSPROPERTY_BOUNDS_LONG
title : KSPROPERTY_BOUNDS_LONG
author : windows-driver-content
description : The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.
old-location : stream\ksproperty_bounds_long.htm
old-project : stream
ms.assetid : 16804ff1-8531-48aa-baf6-b89ccfe25d07
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPROPERTY_BOUNDS_LONG
req.alt-loc : ks.h
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
req.typenames : KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG
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


    ## Remarks
        This structure specifies a range of 32-bit values for a property. Use only when the <b>MembersFlags</b> member of the relevant <a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a> is set to KSPROPERTY_MEMBER_RANGES. Use this structure in the <b>Members</b> array in the relevant <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_BOUNDS_LONG union%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>