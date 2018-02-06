---
UID: NE:ntddndis._NDIS_RECEIVE_QUEUE_TYPE
title: "_NDIS_RECEIVE_QUEUE_TYPE"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_TYPE enumeration identifies the type of a receive queue.
old-location: netvista\ndis_receive_queue_type.htm
old-project: netvista
ms.assetid: 8ee28daf-2719-42bc-ab2e-6dcfa7f0e04b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisReceiveQueueTypeMaximum, NdisReceiveQueueTypeUnspecified, *PNDIS_RECEIVE_QUEUE_TYPE, ntddndis/PNDIS_RECEIVE_QUEUE_TYPE, _NDIS_RECEIVE_QUEUE_TYPE, netvista.ndis_receive_queue_type, ntddndis/NdisReceiveQueueTypeVMQueue, NDIS_RECEIVE_QUEUE_TYPE, ntddndis/NDIS_RECEIVE_QUEUE_TYPE, NDIS_RECEIVE_QUEUE_TYPE enumeration [Network Drivers Starting with Windows Vista], virtual_machine_queue_ref_b51e0e9c-353e-40a1-b466-3136db1fcdd9.xml, ntddndis/NdisReceiveQueueTypeUnspecified, ntddndis/NdisReceiveQueueTypeMaximum, PNDIS_RECEIVE_QUEUE_TYPE, PNDIS_RECEIVE_QUEUE_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], NdisReceiveQueueTypeVMQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_RECEIVE_QUEUE_TYPE
product: Windows
targetos: Windows
req.typenames: "*PNDIS_RECEIVE_QUEUE_TYPE, NDIS_RECEIVE_QUEUE_TYPE"
---

# _NDIS_RECEIVE_QUEUE_TYPE Enumeration
The <b>NDIS_RECEIVE_QUEUE_TYPE</b> enumeration identifies the type of a receive queue.

## Syntax
````
typedef enum _NDIS_RECEIVE_QUEUE_TYPE { 
  NdisReceiveQueueTypeUnspecified,
  NdisReceiveQueueTypeVMQueue,
  NdisReceiveQueueTypeMaximum
} NDIS_RECEIVE_QUEUE_TYPE, *PNDIS_RECEIVE_QUEUE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisReceiveQueueTypeMaximum</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
                </tr>
            
                <tr>
                    <td>NdisReceiveQueueTypeUnspecified</td>
                    <td>The receive queue type is not specified.</td>
                </tr>
            
                <tr>
                    <td>NdisReceiveQueueTypeVMQueue</td>
                    <td>This value specifies a virtual machine (VM) receive queue.</td>
                </tr>
</table>

    ## Remarks

        The NDIS_RECEIVE_QUEUE_TYPE enumeration is used in the 
    <b>QueueType</b> member of the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_parameters.md">
    NDIS_RECEIVE_QUEUE_PARAMETERS</a> and 
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_info.md">
    NDIS_RECEIVE_QUEUE_INFO</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

    ## See Also

        <a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_parameters.md">NDIS_RECEIVE_QUEUE_PARAMETERS</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_info.md">NDIS_RECEIVE_QUEUE_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>