---
UID: NE:fwpsk.FWPS_FIELDS_STREAM_V6_
title: FWPS_FIELDS_STREAM_V6_
author: windows-driver-content
description: The FWPS_FIELDS_STREAM_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_STREAM_V6 and FWPS_LAYER_STREAM_V6_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_stream_v6.htm
old-project: netvista
ms.assetid: a6fd200c-e573-4bca-aa0d-3e4717c7e81c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FWPS_FIELDS_STREAM_V6, FWPS_FIELDS_STREAM_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_STREAM_V6_, FWPS_FIELD_STREAM_V6_DIRECTION, FWPS_FIELD_STREAM_V6_FLAGS, FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_STREAM_V6_IP_LOCAL_PORT, FWPS_FIELD_STREAM_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_STREAM_V6_IP_REMOTE_PORT, FWPS_FIELD_STREAM_V6_MAX, fwpsk/FWPS_FIELDS_STREAM_V6, fwpsk/FWPS_FIELD_STREAM_V6_DIRECTION, fwpsk/FWPS_FIELD_STREAM_V6_FLAGS, fwpsk/FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_STREAM_V6_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_STREAM_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_STREAM_V6_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_STREAM_V6_MAX, netvista.fwps_fields_stream_v6, wfp_ref_5_const_3_data_fields_77276444-32ee-40f1-a227-547aa7c2fd6c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_FIELDS_STREAM_V6
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_STREAM_V6
---

# FWPS_FIELDS_STREAM_V6_ Enumeration
The FWPS_FIELDS_STREAM_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_STREAM_V6 and FWPS_LAYER_STREAM_V6_DISCARD 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layers</a>.

## Syntax
````
typedef enum FWPS_FIELDS_STREAM_V6_ { 
  FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS,
  FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_STREAM_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_STREAM_V6_IP_LOCAL_PORT,
  FWPS_FIELD_STREAM_V6_IP_REMOTE_PORT,
  FWPS_FIELD_STREAM_V6_DIRECTION,
#if (NTDDI_VERSION >= NTDDI_WIN6SP1
  FWPS_FIELD_STREAM_V6_FLAGS,
#endif 
  FWPS_FIELD_STREAM_V6_MAX
} FWPS_FIELDS_STREAM_V6;
````

## Constants

<table>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_COMPARTMENT_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_DIRECTION</td>
                    <td>#####  The possible values are:



#### FWP_DIRECTION_INBOUND



#### FWP_DIRECTION_OUTBOUND</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_FLAGS</td>
                    <td>A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS</td>
                    <td>The local IP address.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_IP_LOCAL_ADDRESS_TYPE</td>
                    <td>The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_IP_LOCAL_PORT</td>
                    <td>The local transport protocol port number.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_IP_REMOTE_ADDRESS</td>
                    <td>The remote IP address.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_IP_REMOTE_PORT</td>
                    <td>The remote transport protocol port number.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_STREAM_V6_MAX</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Unless otherwise noted, supported starting with Windows Vista. Unless otherwise noted, supported starting with Windows Vista. |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_STREAM_V6 enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>