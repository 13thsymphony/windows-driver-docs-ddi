---
UID : NS:charging._CONFIGURABLE_CHARGER_PROPERTY_HEADER
title : _CONFIGURABLE_CHARGER_PROPERTY_HEADER
author : windows-driver-content
description : The CONFIGURABLE_CHARGER_PROPERTY_HEADER structure is a header that is used to create your own structure as an input to IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY.
old-location : battery\configurable_charger_property_header.htm
old-project : battery
ms.assetid : 1A188828-51CE-4C80-92CB-2C01861082CD
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _CONFIGURABLE_CHARGER_PROPERTY_HEADER, *PCONFIGURABLE_CHARGER_PROPERTY_HEADER, CONFIGURABLE_CHARGER_PROPERTY_HEADER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : charging.h
req.include-header : Charging.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CONFIGURABLE_CHARGER_PROPERTY_HEADER
req.alt-loc : charging.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : "*PCONFIGURABLE_CHARGER_PROPERTY_HEADER, CONFIGURABLE_CHARGER_PROPERTY_HEADER"
---

# _CONFIGURABLE_CHARGER_PROPERTY_HEADER structure
The CONFIGURABLE_CHARGER_PROPERTY_HEADER structure is a header that is used to create your own structure as an input to <a href="..\charging\ni-charging-ioctl_internal_configure_charger_property.md">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>.

## Syntax
````
typedef struct _CONFIGURABLE_CHARGER_PROPERTY_HEADER {
  ULONG Size;
  GUID  ChargerId;
  ULONG PropertyId;
} CONFIGURABLE_CHARGER_PROPERTY_HEADER, *PCONFIGURABLE_CHARGER_PROPERTY_HEADER;
````

## Members

        
            `ChargerId`

            The charger ID.
        
            `PropertyId`

            The ID of the property to be configured.
        
            `Size`

            Size of the structure.

    ## Remarks
        Extend this structure to add your own values for the input to <a href="..\charging\ni-charging-ioctl_internal_configure_charger_property.md">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>. Create a new structure with <b>CONFIGURABLE_CHARGER_PROPERTY_HEADER</b> as the first field, and one or more values after it that correspond to your <b>PropertyId</b>. Here are two example structures.

Make sure you set <b>Header.Size</b> to the appropriate size of your new structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | charging.h (include Charging.h) |

    ## See Also

        <dl>
<dt>
<a href="..\charging\ni-charging-ioctl_internal_configure_charger_property.md">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20CONFIGURABLE_CHARGER_PROPERTY_HEADER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>