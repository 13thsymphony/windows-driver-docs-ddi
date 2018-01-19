---
UID : NS:61883._CMP_GET_PLUG_STATE
title : _CMP_GET_PLUG_STATE
author : windows-driver-content
description : This structure is used in getting the state of a plug.
old-location : ieee\cmp_get_plug_state.htm
old-project : IEEE
ms.assetid : 76BC179A-7484-433C-8467-B13BA7008B90
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _CMP_GET_PLUG_STATE, CMP_GET_PLUG_STATE, *PCMP_GET_PLUG_STATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 61883.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CMP_GET_PLUG_STATE
req.alt-loc : 61883.h
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
req.typenames : CMP_GET_PLUG_STATE, *PCMP_GET_PLUG_STATE
---

# _CMP_GET_PLUG_STATE structure
This structure is used in getting the state of a plug.The  request retrieves state information for the specified plug, including its current connections and bus data format. Plug state is volatile and can change unexpectedly.

## Syntax
````
typedef struct _CMP_GET_PLUG_STATE {
  HANDLE hPlug;
  ULONG  State;
  ULONG  DataRate;
  ULONG  Payload;
  ULONG  BC_Connections;
  ULONG  PP_Connections;
} CMP_GET_PLUG_STATE, *PCMP_GET_PLUG_STATE;
````

## Members

        
            `BC_Connections`

            On output, the number of broadcast connections associated with the plug.
        
            `DataRate`

            On output, the data rate of the plug. Can be one of the following: 

CMP_SPEED_S100 

CMP_SPEED_S200 

CMP_SPEED_S400
        
            `hPlug`

            On input, the handle of the plug to retrieve state information.
        
            `Payload`

            On output, the payload size for the plug.
        
            `PP_Connections`

            On output, the number of point-to-point connections associated with the plug.
        
            `State`

            On output, the state of the plug. Can be one of the following:

CMP_PLUG_STATE_IDLE 

CMP_PLUG_STATE_READY 

CMP_PLUG_STATE_SUSPENDED 

CMP_PLUG_STATE_ACTIVE

    ## Remarks
        If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | 61883.h |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_GET_PLUG_STATE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>