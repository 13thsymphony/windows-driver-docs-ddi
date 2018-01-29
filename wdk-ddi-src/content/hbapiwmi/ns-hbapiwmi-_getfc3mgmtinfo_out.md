---
UID : NS:hbapiwmi._GetFC3MgmtInfo_OUT
title : _GetFC3MgmtInfo_OUT
author : windows-driver-content
description : The GetFC3MgmtInfo_OUT structure is used to report the output parameter data of the GetFC3MgmtInfo WMI method to the WMI client.
old-location : storage\getfc3mgmtinfo_out.htm
old-project : storage
ms.assetid : 5cce25e7-582b-49b3-9f10-be59471e377f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.getfc3mgmtinfo_out, structs-Fibre_599fab97-a877-4299-8697-1decb1305672.xml, GetFC3MgmtInfo_OUT structure [Storage Devices], _GetFC3MgmtInfo_OUT, hbapiwmi/PGetFC3MgmtInfo_OUT, PGetFC3MgmtInfo_OUT, hbapiwmi/GetFC3MgmtInfo_OUT, GetFC3MgmtInfo_OUT, PGetFC3MgmtInfo_OUT structure pointer [Storage Devices], *PGetFC3MgmtInfo_OUT
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PGetFC3MgmtInfo_OUT, GetFC3MgmtInfo_OUT"
---

# _GetFC3MgmtInfo_OUT structure
The GetFC3MgmtInfo_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553939">GetFC3MgmtInfo</a> WMI method to the WMI client.

## Syntax
````
typedef struct _GetFC3MgmtInfo_OUT {
  ULONG          HBAStatus;
  HBAFC3MgmtInfo MgmtInfo;
} GetFC3MgmtInfo_OUT, *PGetFC3MgmtInfo_OUT;
````

## Members


`HBAStatus`

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation.

`MgmtInfo`

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafc3mgmtinfo.md">HBAFC3MgmtInfo</a> that reports FC3 management information.

## Remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553939">GetFC3MgmtInfo</a> method reports fibre channel-3 management information.

The WMI tool suite generates a declaration of the GetEventBuffer_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="..\hbapiwmi\ns-hbapiwmi-_hbafc3mgmtinfo.md">HBAFC3MgmtInfo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553939">GetFC3MgmtInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFC3MgmtInfo_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>