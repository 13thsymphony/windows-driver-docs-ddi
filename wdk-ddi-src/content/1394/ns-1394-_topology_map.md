---
UID : NS:1394._TOPOLOGY_MAP
title : _TOPOLOGY_MAP
author : windows-driver-content
description : The TOPOLOGY_MAP structure is used to store an IEEE 1394 bus topology map. The relations between devices are found in the port members of the entries in TOP_Self_ID_Array.
old-location : ieee\topology_map.htm
old-project : IEEE
ms.assetid : 0a4c7ffc-94f9-4068-b650-1da43e45d0ad
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _TOPOLOGY_MAP, TOPOLOGY_MAP, *PTOPOLOGY_MAP
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 1394.h
req.include-header : 1394.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : TOPOLOGY_MAP
req.alt-loc : 1394.h
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
req.typenames : TOPOLOGY_MAP, *PTOPOLOGY_MAP
---

# _TOPOLOGY_MAP structure
The TOPOLOGY_MAP structure is used to store an IEEE 1394 bus topology map. The relations between devices are found in the port members of the entries in <b>TOP_Self_ID_Array</b>.

## Syntax
````
typedef struct _TOPOLOGY_MAP {
  USHORT  TOP_Length;
  USHORT  TOP_CRC;
  ULONG   TOP_Generation;
  USHORT  TOP_Node_Count;
  USHORT  TOP_Self_ID_Count;
  SELF_ID TOP_Self_ID_Array[1];
} TOPOLOGY_MAP, *PTOPOLOGY_MAP;
````

## Members

        
            `TOP_CRC`

            Specifies the CRC value for the topology map.
        
            `TOP_Generation`

            Specifies the bus reset generation for which the topology map was created.
        
            `TOP_Length`

            Specifies the length in quadlets of the topology map.
        
            `TOP_Node_Count`

            Specifies the number of nodes in the topology map.
        
            `TOP_Self_ID_Array`

            Pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff538073">SELF_ID</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff538080">SELF_ID_MORE</a> structures (the two structures are the same size).
        
            `TOP_Self_ID_Count`

            Specifies the number of entries in <b>TOP_Self_ID_Array</b>.

    ## Remarks
        All data will be in big-endian format.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | 1394.h (include 1394.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537646">REQUEST_GET_SPEED_TOPOLOGY_MAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20TOPOLOGY_MAP structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>