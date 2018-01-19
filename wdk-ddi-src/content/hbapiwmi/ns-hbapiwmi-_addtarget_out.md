---
UID : NS:hbapiwmi._AddTarget_OUT
title : _AddTarget_OUT
author : windows-driver-content
description : The AddTarget_OUT structure is used by a WMI provider to report the output parameter data of the AddTarget WMI method to the WMI client.
old-location : storage\addtarget_out.htm
old-project : storage
ms.assetid : 1e0f19df-1705-4a70-a47c-0569907330a4
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _AddTarget_OUT, *PAddTarget_OUT, AddTarget_OUT
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
req.alt-api : AddTarget_OUT
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
req.typenames : "*PAddTarget_OUT, AddTarget_OUT"
---

# _AddTarget_OUT structure
The AddTarget_OUT structure is used by a WMI provider to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550136">AddTarget</a> WMI method to the WMI client.

## Syntax
````
typedef struct _AddTarget_OUT {
  ULONG HBAStatus;
} AddTarget_OUT, *PAddTarget_OUT;
````

## Members

        
            `HBAStatus`

            Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550136">AddTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddTarget_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>