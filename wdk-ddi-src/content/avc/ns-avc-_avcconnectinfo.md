---
UID : NS:avc._AVCCONNECTINFO
title : "_AVCCONNECTINFO"
author : windows-driver-content
description : The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections.
old-location : stream\avcconnectinfo.htm
old-project : stream
ms.assetid : ed6e01f0-fa30-4a42-8271-70afb2fde8c9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PAVCCONNECTINFO structure pointer [Streaming Media Devices], AVCCONNECTINFO, stream.avcconnectinfo, *PAVCCONNECTINFO, avc/AVCCONNECTINFO, _AVCCONNECTINFO, AVCCONNECTINFO structure [Streaming Media Devices], avcref_41c8705a-5735-4ab2-87f0-02b55b128c23.xml, PAVCCONNECTINFO, avc/PAVCCONNECTINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : avc.h
req.include-header : Avc.h
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
req.typenames : AVCCONNECTINFO, *PAVCCONNECTINFO
---

# _AVCCONNECTINFO structure
The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections.

## Syntax
````
typedef struct _AVCCONNECTINFO {
  GUID           DeviceID;
  UCHAR          SubunitAddress[AVCCONNECTINFO_MAX_SUBUNITADDR_LEN];
  ULONG          SubunitPlugNumber;
  KSPIN_DATAFLOW DataFlow;
  HANDLE         hPlug;
  ULONG          UnitPlugNumber;
} AVCCONNECTINFO, *PAVCCONNECTINFO;
````

## Members


`DataFlow`

The direction of data flow on this subunit plug. Destination plugs have KSPIN_DATAFLOW_IN; source plugs have KSPIN_DATAFLOW_OUT.

`DeviceID`

A GUID representing the unit as a whole. All subunits within the same unit share the same GUID. No two units share the same GUID.

`hPlug`

A plug handle obtained from <i>61883.sys</i> by the intersect handler according to the bit flags set in the associated AVCPRECONNECTINFO structure for this pin. If the proposed connection is between two subunits within the same unit, this value is <b>NULL</b>.

`SubunitAddress`

The encoded subunit type and subunit ID of the subunit.

`SubunitPlugNumber`

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.

`UnitPlugNumber`

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.

## Remarks
This structure is used only as member inside the <a href="..\avc\ns-avc-_avc_setconnect_info.md">AVC_SETCONNECT_INFO</a> structure. It is not used by itself.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | avc.h (include Avc.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVCCONNECTINFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>