---
UID : NS:ndiswwan._NDIS_WWAN_PROVISIONED_CONTEXTS
title : _NDIS_WWAN_PROVISIONED_CONTEXTS
author : windows-driver-content
description : The NDIS_WWAN_PROVISIONED_CONTEXTS structure represents a list of provisioned contexts and the number of provisioned contexts in the list.
old-location : netvista\ndis_wwan_provisioned_contexts.htm
old-project : netvista
ms.assetid : ee4ba781-9adf-4eb0-8c3d-b11aac86c943
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_WWAN_PROVISIONED_CONTEXTS, *PNDIS_WWAN_PROVISIONED_CONTEXTS, NDIS_WWAN_PROVISIONED_CONTEXTS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndiswwan.h
req.include-header : Ndiswwan.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with  Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_WWAN_PROVISIONED_CONTEXTS
req.alt-loc : ndiswwan.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PNDIS_WWAN_PROVISIONED_CONTEXTS, NDIS_WWAN_PROVISIONED_CONTEXTS"
---

# _NDIS_WWAN_PROVISIONED_CONTEXTS structure
The NDIS_WWAN_PROVISIONED_CONTEXTS structure represents a list of provisioned contexts and the number
  of provisioned contexts in the list.

## Syntax
````
typedef struct _NDIS_WWAN_PROVISIONED_CONTEXTS {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_LIST_HEADER   ContextListHeader;
} NDIS_WWAN_PROVISIONED_CONTEXTS, *PNDIS_WWAN_PROVISIONED_CONTEXTS;
````

## Members

        
            `ContextListHeader`

            A formatted 
     <a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a> object that represents a
     list of provisioned contexts and the number of provisioned contexts in the list.
        
            `Header`

            The header with type, revision, and size information about the NDIS_WWAN_PROVISIONED_CONTEXTS
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_PROVISIONED_CONTEXTS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PROVISIONED_CONTEXTS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.
        
            `uStatus`

            The status of the provisioned context query or set operation. The following table shows the possible values for
     this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
 The  operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed for a reason other than those listed here.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_PARAMETERS

</td>
<td>
The operation failed because of invalid parameters.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The operation failed because the device requires a PIN.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a bad SIM card was detected.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
The operation failed because the SIM card was not inserted fully into the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because the device does not support service activation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to 
        <b>WwanReadyStateInitialized</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_READ_FAILURE

</td>
<td>
The operation failed because the device was unable to get provisioned contexts.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_WRITE_FAILURE

</td>
<td>
The operation failed because the update request was unsuccessful.

</td>
</tr>
</table>
 

The status of provisioned context set operation. The following table shows the possible value for
     this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_WRITE_FAILURE

</td>
<td>
The operation failed because the update request was unsuccessful.

</td>
</tr>
</table>

    ## Remarks
        Miniport drivers should specify zero elements in the context list when they respond to
    OID_WWAN_PROVISIONED_CONTEXT 
    <i>set</i> requests.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_PROVISIONED_CONTEXTS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>