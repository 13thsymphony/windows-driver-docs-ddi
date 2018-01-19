---
UID : NS:windot11._DOT11_ADDITIONAL_IE
title : _DOT11_ADDITIONAL_IE
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11_additional_ie.htm
old-project : netvista
ms.assetid : db034863-f5fa-42bb-81c8-23d4784e0abe
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _DOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE, DOT11_ADDITIONAL_IE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DOT11_ADDITIONAL_IE
req.alt-loc : windot11.h
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
req.typenames : "*PDOT11_ADDITIONAL_IE, DOT11_ADDITIONAL_IE"
req.product : Windows 10 or later.
---

# _DOT11_ADDITIONAL_IE structure


## Syntax
````
typedef struct _DOT11_ADDITIONAL_IE {
  NDIS_OBJECT_HEADER Header;
  ULONG              uBeaconIEsOffset;
  ULONG              uBeaconIEsLength;
  ULONG              uResponseIEsOffset;
  ULONG              uResponseIEsLength;
} DOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE;
````

## Members

        
            `Header`

            The type, revision, and size of the DOT11_ADDITIONAL_IE structure. This member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:
        
            `uBeaconIEsLength`

            The length of the additional IEs, in bytes, in the beacon frame sent by the NIC. The default value
     is 0.
        
            `uBeaconIEsOffset`

            The offset of the additional IEs, in bytes, in the beacon frame sent by the NIC. This offset is
     relative to the start of the buffer that contains the DOT11_ADDITIONAL_IE structure. The default value
     is 0.
        
            `uResponseIEsLength`

            The length of the additional IEs, in bytes, in the probe response frame sent by the NIC. The
     default value is 0.
        
            `uResponseIEsOffset`

            The offset of the additional IEs, in bytes, in the probe response frame sent by the NIC. This
     offset is relative to the start of the buffer that contains the DOT11_ADDITIONAL_IE structure. The
     default value is 0.

    ## Remarks
        This structure is used with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569103">OID_DOT11_ADDITIONAL_IE</a>.

The miniport driver should reset the members of the DOT11_ADDITIONAL_IE structure to the default
    values when it receives an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Ndis.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569103">OID_DOT11_ADDITIONAL_IE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ADDITIONAL_IE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>