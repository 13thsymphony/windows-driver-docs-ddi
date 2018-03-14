---
UID: NF:portcls.IRegistryKey.QueryRegistryValues
title: IRegistryKey::QueryRegistryValues method
author: windows-driver-content
description: The QueryRegistryValues method allows the caller to query several values from the registry with a single call.
old-location: audio\iregistrykey_queryregistryvalues.htm
old-project: audio
ms.assetid: eb3aa7ec-65f7-4e3d-8059-e9627de9818c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IRegistryKey, IRegistryKey interface [Audio Devices], QueryRegistryValues method, IRegistryKey::QueryRegistryValues, QueryRegistryValues method [Audio Devices], QueryRegistryValues method [Audio Devices], IRegistryKey interface, QueryRegistryValues,IRegistryKey.QueryRegistryValues, audio.iregistrykey_queryregistryvalues, audmp-routines_b2601a0c-3b8f-4e2b-868c-cf189eca7e05.xml, portcls/IRegistryKey::QueryRegistryValues
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IRegistryKey.QueryRegistryValues
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# QueryRegistryValues method
The <code>QueryRegistryValues</code> method allows the caller to query several values from the registry with a single call.

## Syntax

````
NTSTATUS QueryRegistryValues(
  [in]           PRTL_QUERY_REGISTRY_TABLE QueryTable,
  [in, optional] PVOID                     Context
);
````

## Parameters

`QueryTable`

Pointer to an array of one or more RTL_QUERY_REGISTRY_TABLE structures. (This structure is described in <a href="..\wdm\nf-wdm-rtlqueryregistryvalues.md">RtlQueryRegistryValues</a>.) Each structure specifies the value name and subkey name for a registry entry that the caller is querying. Each structure also contains a function pointer to a caller-supplied <b>QueryRoutine</b> callback that the <code>QueryRegistryValues</code> method will call with information about the corresponding registry entry. The array must be terminated by a structure with a <b>Name</b> member that is <b>NULL</b>.

`Context`

This is a caller-defined context value. The <code>QueryRegistryValues</code> method passes this value as a call parameter to each of the <b>QueryRoutine</b> callbacks. The context value is typically a pointer to a caller-defined structure containing context data that the caller's <b>QueryRoutine</b> accesses. The context value is cast to pointer type PVOID, but the <code>QueryRegistryValues</code> method performs no validation of the pointer.


## Return Value

<code>QueryRegistryValues</code> returns STATUS_SUCCESS if the call was successful in processing the entire <i>QueryTable</i>. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <i>QueryTable</i> parameter that was passed to the method is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the method was unable to find the object that was specified in one of the <i>QueryTable</i> entries.

</td>
</tr>
</table>

## Remarks

This method uses caller-supplied callback routines to enumerate the values of a list of registry entries. If successful, the method returns after calling all the callback routines in the list.

The <i>QueryTable</i> parameter points to an array of RTL_QUERY_REGISTRY_TABLE structures. The first member of this structure, <b>QueryRoutine</b>, is a function pointer to a caller-supplied callback routine. For more information, see <a href="..\wdm\nf-wdm-rtlqueryregistryvalues.md">RtlQueryRegistryValues</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nn-portcls-iregistrykey.md">IRegistryKey</a>



<a href="..\wdm\nf-wdm-rtlqueryregistryvalues.md">RtlQueryRegistryValues</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IRegistryKey::QueryRegistryValues method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>