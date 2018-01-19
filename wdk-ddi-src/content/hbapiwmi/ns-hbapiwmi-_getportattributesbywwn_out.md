---
UID : NS:hbapiwmi._GetPortAttributesByWWN_OUT
title : _GetPortAttributesByWWN_OUT
author : windows-driver-content
description : The GetPortAttributesByWWN_OUT structure is used to report the output parameter data of the GetPortAttributesByWWN WMI method to the WMI client.
old-location : storage\getportattributesbywwn_out.htm
old-project : storage
ms.assetid : 9a4d04de-2c44-4f13-ac6f-32e2fe879e4e
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _GetPortAttributesByWWN_OUT, *PGetPortAttributesByWWN_OUT, GetPortAttributesByWWN_OUT
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
req.alt-api : GetPortAttributesByWWN_OUT
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
req.typenames : "*PGetPortAttributesByWWN_OUT, GetPortAttributesByWWN_OUT"
---

# _GetPortAttributesByWWN_OUT structure
The GetPortAttributesByWWN_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554965">GetPortAttributesByWWN</a> WMI method to the WMI client.

## Syntax
````
typedef struct _GetPortAttributesByWWN_OUT {
  ULONG                         HBAStatus;
  MSFC_HBAPortAttributesResults PortAttributes;
} GetPortAttributesByWWN_OUT, *PGetPortAttributesByWWN_OUT;
````

## Members

        
            `HBAStatus`

            Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation.
        
            `PortAttributes`

            Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_msfc_hbaportattributesresults.md">MSFC_HBAPortAttributesResults</a> that holds the port attributes to be reported.

    ## Remarks
        The WMI tool suite generates a declaration of the GetPortAttributesByWWN_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554965">GetPortAttributesByWWN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
<dt>
<a href="..\hbapiwmi\ns-hbapiwmi-_msfc_hbaportattributesresults.md">MSFC_HBAPortAttributesResults</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetPortAttributesByWWN_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>