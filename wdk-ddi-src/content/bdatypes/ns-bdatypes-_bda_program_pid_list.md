---
UID: NS:bdatypes._BDA_PROGRAM_PID_LIST
title: "_BDA_PROGRAM_PID_LIST"
author: windows-driver-content
description: The BDA_PROGRAM_PID_LIST structure describes data of a specific program to view. This data consists of packets that are identified with packet identifiers (PID).
old-location: stream\bda_program_pid_list.htm
old-project: stream
ms.assetid: d3a96377-71f9-40ba-a15f-cacd64dcc6c4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.bda_program_pid_list, BDA_PROGRAM_PID_LIST structure [Streaming Media Devices], bdatypes/PBDA_PROGRAM_PID_LIST, *PBDA_PROGRAM_PID_LIST, PBDA_PROGRAM_PID_LIST structure pointer [Streaming Media Devices], BDA_PROGRAM_PID_LIST, _BDA_PROGRAM_PID_LIST, bdaref_a78db54e-c75e-46dc-8b81-f97163569450.xml, bdatypes/BDA_PROGRAM_PID_LIST, PBDA_PROGRAM_PID_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	bdatypes.h
apiname:
-	BDA_PROGRAM_PID_LIST
product: Windows
targetos: Windows
req.typenames: "*PBDA_PROGRAM_PID_LIST, BDA_PROGRAM_PID_LIST"
---

# _BDA_PROGRAM_PID_LIST structure
The BDA_PROGRAM_PID_LIST structure describes data of a specific program to view. This data consists of packets that are identified with packet identifiers (PID).

## Syntax
````
typedef struct _BDA_PROGRAM_PID_LIST {
  ULONG ulProgramNumber;
  ULONG ulcPIDs;
  ULONG ulPID[MIN_DIMENSION];
} BDA_PROGRAM_PID_LIST, *PBDA_PROGRAM_PID_LIST;
````

## Members


`ulcPIDs`

Number of PIDs in the <b>ulPID</b> array.

`ulPID`

Array of PIDs that identify packets of program data.

`ulProgramNumber`

Number of the program to be viewed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h (include Bdatypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564298">KSPROPERTY_BDA_CA_SET_PROGRAM_PIDS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566536">KSPROPSETID_BdaCA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_PROGRAM_PID_LIST structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>