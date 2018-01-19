---
UID : NS:hbapiwmi._GetFcpPersistentBinding_OUT
title : _GetFcpPersistentBinding_OUT
author : windows-driver-content
description : The GetFcpPersistentBinding_OUT structure is used to report the output parameter data of the GetFcpPersistentBinding WMI method to the WMI client.
old-location : storage\getfcppersistentbinding_out.htm
old-project : storage
ms.assetid : 1bb7c529-df26-4173-a098-6a19adf6b569
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _GetFcpPersistentBinding_OUT, GetFcpPersistentBinding_OUT, *PGetFcpPersistentBinding_OUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GetFcpPersistentBinding_OUT
req.alt-loc : hbapiwmi.h
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
req.typenames : GetFcpPersistentBinding_OUT, *PGetFcpPersistentBinding_OUT
---

# _GetFcpPersistentBinding_OUT structure
The GetFcpPersistentBinding_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method to the WMI client.

## Syntax
````
typedef struct _GetFcpPersistentBinding_OUT {
  ULONG              HBAStatus;
  ULONG              TotalEntryCount;
  ULONG              OutEntryCount;
  HBAFCPBindingEntry Entry[1];
} GetFcpPersistentBinding_OUT, *PGetFcpPersistentBinding_OUT;
````

## Members

        
            `Entry`

            Contains an array of structures of type HBAFCPBindingEntry that describe an HBA's bindings between operating system and fibre channel protocol (FCP) identifiers.
        
            `HBAStatus`

            Contains the status of the operation. For a list of allowed values and their descriptions, see HBA_STATUS.
        
            `OutEntryCount`

            Indicates the total number of mappings retrieved by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> WMI method. This value will be less than or equal to <b>TotalEntryCount</b>.
        
            `TotalEntryCount`

            Indicates the total number of persistent bindings retrieved by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method.

    ## Remarks
        The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method retrieves the bindings between SCSI and fibre channel protocol (FCP) identifiers for the logical units.

The WMI tool suite generates a declaration of the GetFcpPersistentBinding_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFcpPersistentBinding_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>