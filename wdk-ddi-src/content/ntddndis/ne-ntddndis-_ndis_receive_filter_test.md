---
UID: NE:ntddndis._NDIS_RECEIVE_FILTER_TEST
title: "_NDIS_RECEIVE_FILTER_TEST"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_TEST enumeration identifies the type of test that the receive filter performs.
old-location: netvista\ndis_receive_filter_test.htm
old-project: netvista
ms.assetid: 064d8335-3ebf-4bc2-901e-10ce46bf7732
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_TEST, NDIS_RECEIVE_FILTER_TEST, NDIS_RECEIVE_FILTER_TEST enumeration [Network Drivers Starting with Windows Vista], NdisReceiveFilterTestEqual, NdisReceiveFilterTestMaskEqual, NdisReceiveFilterTestMaximum, NdisReceiveFilterTestNotEqual, NdisReceiveFilterTestUndefined, PNDIS_RECEIVE_FILTER_TEST, PNDIS_RECEIVE_FILTER_TEST enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_TEST, netvista.ndis_receive_filter_test, ntddndis/NDIS_RECEIVE_FILTER_TEST, ntddndis/NdisReceiveFilterTestEqual, ntddndis/NdisReceiveFilterTestMaskEqual, ntddndis/NdisReceiveFilterTestMaximum, ntddndis/NdisReceiveFilterTestNotEqual, ntddndis/NdisReceiveFilterTestUndefined, ntddndis/PNDIS_RECEIVE_FILTER_TEST, virtual_machine_queue_ref_16206d46-2048-429b-b7cf-aa5f5d099ae1.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_FILTER_TEST
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_TEST, *PNDIS_RECEIVE_FILTER_TEST
---

# _NDIS_RECEIVE_FILTER_TEST Enumeration
The <b>NDIS_RECEIVE_FILTER_TEST</b> enumeration identifies the type of test that the receive filter
  performs.

## Syntax
```
typedef enum _NDIS_RECEIVE_FILTER_TEST {
  NdisReceiveFilterTestUndefined  ,
  NdisReceiveFilterTestEqual      ,
  NdisReceiveFilterTestMaskEqual  ,
  NdisReceiveFilterTestNotEqual   ,
  NdisReceiveFilterTestMaximum
} NDIS_RECEIVE_FILTER_TEST, *PNDIS_RECEIVE_FILTER_TEST;
```

## Constants

<table>
            
                <tr>
                    <td>NdisReceiveFilterTestUndefined</td>
                    <td>The type of test is not specified.</td>
                </tr>
            
                <tr>
                    <td>NdisReceiveFilterTestEqual</td>
                    <td>The network adapter tests the selected header field to determine whether it is equal to a specific
     value.</td>
                </tr>
            
                <tr>
                    <td>NdisReceiveFilterTestMaskEqual</td>
                    <td>The network adapter supports masking (that is, a bitwise AND) of the selected header field to
     determine whether the result is equal to a specific value.</td>
                </tr>
            
                <tr>
                    <td>NdisReceiveFilterTestNotEqual</td>
                    <td>The network adapter tests the selected header field to determine whether it is not equal to a specific
     value.</td>
                </tr>
            
                <tr>
                    <td>NdisReceiveFilterTestMaximum</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
                </tr>
</table>

## Remarks

The NDIS_RECEIVE_FILTER_TEST enumeration is used in the 
    <a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>