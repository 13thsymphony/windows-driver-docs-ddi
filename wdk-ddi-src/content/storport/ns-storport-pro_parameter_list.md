---
UID : NS:storport.PRO_PARAMETER_LIST
title : PRO_PARAMETER_LIST
author : windows-driver-content
description : The PRO_PARAMETER_LIST structure is sent in a Persistent Reserve Out command to a device server.
old-location : storage\pro_parameter_list.htm
old-project : storage
ms.assetid : 96c128e1-c38a-412f-adeb-cde820e1af4e
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PRO_PARAMETER_LIST, PRO_PARAMETER_LIST, *PPRO_PARAMETER_LIST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : storport.h
req.include-header : Ntddstor.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PRO_PARAMETER_LIST
req.alt-loc : storport.h
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
req.typenames : PRO_PARAMETER_LIST, *PPRO_PARAMETER_LIST
req.product : Windows 10 or later.
---

# PRO_PARAMETER_LIST structure
The PRO_PARAMETER_LIST structure is sent in a Persistent Reserve Out command to a device server.

## Syntax
````
typedef struct {
  UCHAR ReservationKey[8];
  UCHAR ServiceActionReservationKey[8];
  UCHAR ScopeSpecificAddress[4];
  UCHAR ActivatePersistThroughPowerLoss  :1;
  UCHAR Reserved1  :7;
  UCHAR Reserved2;
  UCHAR Obsolete[2];
} PRO_PARAMETER_LIST, *PPRO_PARAMETER_LIST;
````

## Members

        
            `ActivatePersistThroughPowerLoss`

            The ActivatePersistThroughPowerLoss (APTPL) bit is valid only for the following service actions:

<ul>
<li>
REGISTER

</li>
<li>
REGISTER AND IGNORE EXISTING KEY

</li>
</ul>
        
            `Obsolete`

            Reserved. Must be zero.
        
            `ReservationKey`

            The ReservationKey field contains an 8-byte value that is provided by the application client to the device server. This value identifies the initiator that is the source of the Persistent Reserve Out command.
        
            `Reserved1`

            Reserved. Must be zero.
        
            `Reserved2`

            Reserved. Must be zero.
        
            `ScopeSpecificAddress`

            The ScopeSpecificAddress field contains the element address that has zeros placed in the most significant bits to fit the field. This is true if the scope of a reservation is set to ELEMENT_SCOPE. Otherwise, this field is set to all zeros.
        
            `ServiceActionReservationKey`

            The ServiceActionReservationKey field contains information that is needed for the following four service actions:

<ul>
<li>
REGISTER

</li>
<li>
REGISTER AND IGNORE EXISTING KEY

</li>
<li>
PREEMPT

</li>
<li>
PREEMPT AND ABORT

</li>
</ul>

    ## Remarks
        The <a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_out.md">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a> request is used to control information about persistent reservations and reservation keys that are active within a device server.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Ntddstor.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_out.md">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PRO_PARAMETER_LIST structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>