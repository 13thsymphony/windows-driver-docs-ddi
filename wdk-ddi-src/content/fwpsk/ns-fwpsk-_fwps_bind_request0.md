---
UID: NS:fwpsk._FWPS_BIND_REQUEST0
title: _FWPS_BIND_REQUEST0
author: windows-driver-content
description: The FWPS_BIND_REQUEST0 structure defines modifiable data for the FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V4 and FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V6 layers.
old-location: netvista\fwps_bind_request0.htm
old-project: netvista
ms.assetid: 1a311470-b443-41d8-866f-10bf3120c13c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _FWPS_BIND_REQUEST0, FWPS_BIND_REQUEST0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_BIND_REQUEST0
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_BIND_REQUEST0
---

# _FWPS_BIND_REQUEST0 structure



## -description
The <b>FWPS_BIND_REQUEST0</b> structure defines modifiable data for the FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V4
  and FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V6 layers. The callout driver uses this data to inspect or modify the
  connection information.



## -syntax

````
typedef struct _FWPS_BIND_REQUEST0 {
  SOCKADDR_STORAGE           localAddressAndPort;
  UINT64                     portReservationToken;
  struct _FWPS_BIND_REQUEST0  *previousVersion;
  UINT64                     modifierFilterId;
} FWPS_BIND_REQUEST0;
````


## -struct-fields

### -field localAddressAndPort

The local transport address of the bind request. This is an IPV4 or IPV6 address and TCP/UDP port
     formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a> structure.


### -field portReservationToken

A token used to reserve the appropriate port. The token is obtained when a port is reserved by
     calling either 
     <a href="https://msdn.microsoft.com/19DAF828-B0E4-49E2-843D-7350C8083C45">CreatePersistentTcpPortReservation</a> or 
     <a href="https://msdn.microsoft.com/AFD2EFD1-55AF-49C9-8109-D4D1B7BB7C94">CreatePersistentUdpPortReservation</a>. Both reservation functions can be found in iphlpapi.h.


### -field previousVersion

The previous version of the bind request data. This read-only field records the modification history of the bind request. This member is preinitialized with a pointer to a singly linked list with the index set to the record for the current FWPS_BIND_REQUEST0 data.



### -field modifierFilterId

The value of the 
     <b>FilterId</b> member of the 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function's 
     <i>filter</i> parameter. For more information about the 
     <b>FilterId</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>.


## -remarks
The callout driver obtains this structure by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
    FwpsAcquireWritableLayerDataPointer0</a> function, which returns a pointer to a <b>FWPS_BIND_REQUEST0</b>
    structure through the 
    <i>writableLayerData</i> parameter.

The 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function can modify the bind
    request's parameters, such as redirecting the local transport address or port to another address or port. If
    it modifies the bind request's parameters, the  
    <i>classifyFn</i> function must do the following:

Make all changes to the <b>FWPS_BIND_REQUEST0</b> structure that was returned by
      <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">FwpsAcquireWritableLayerDataPointer0</a>. Only the 
      <b>localAddressAndPort</b> and 
      <b>portReservationToken</b> members can be modified.

Call 
      <a href="..\fwpsk\nf-fwpsk-fwpsapplymodifiedlayerdata0.md">
      FwpsApplyModifiedLayerData0</a> with the 
      <i>modifiedLayerData</i> parameter set to the address of the <b>FWPS_BIND_REQUEST0</b> structure, even if the callout driver didn't modify any data. This value
      must be the same as the 
      <i>modifiedLayerData</i> parameter value that was returned by 
      <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
      FwpsAcquireWritableLayerDataPointer0</a>.

This structure acts as a linked list that contains a record of all changes made by other callout
    drivers. There is previous version information if the 
    <b>previousVersion</b> member is not <b>NULL</b>. To examine the complete version history, the callout driver
    must continue to examine the 
    <b>previousVersion</b> member of each structure in the list until it is finds a node that has this member set to a value of <b>NULL</b>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 7.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsapplymodifiedlayerdata0.md">FwpsApplyModifiedLayerData0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
   FwpsAcquireWritableLayerDataPointer0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_BIND_REQUEST0 structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

