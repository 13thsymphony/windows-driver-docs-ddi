---
UID: NC.wlanihv.DOT11EXT_POST_ASSOCIATE_COMPLETION
title: DOT11EXT_POST_ASSOCIATE_COMPLETION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extpostassociatecompletion.htm
old-project: netvista
ms.assetid: 25db270c-3de8-4ced-82f1-2cd778006538
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _BINARY_CONTAINER, BINARY_CONTAINER, *PBINARY_CONTAINER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtPostAssociateCompletion
req.alt-loc: wlanihv.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# DOT11EXT_POST_ASSOCIATE_COMPLETION callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtPostAssociateCompletion(
  _In_opt_ HANDLE             hDot11SvcHandle,
  _In_opt_ HANDLE             hSecuritySessionID,
  _In_opt_ PDOT11_MAC_ADDRESS pPeer,
  _In_     DWORD              dwReasonCode,
  _In_     DWORD              dwWin32Error
);
````


## -parameters

### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hSecuritySessionID [in, optional]

The handle of the security session identifier (ID) returned through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
     Dot11ExtIhvPerformPostAssociate</a> IHV Handler function.


### -param pPeer [in, optional]

The media access control (MAC) address of the access point (AP) with which the IHV Extensions DLL
     performed a security operation. This parameter is formatted as a 
     <a href="netvista.dot11_mac_address">DOT11_MAC_ADDRESS</a> structure.
     

<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div>
<div> </div>

### -param dwReasonCode [in]

A value that provides additional information for the completion status of the post-association
     operation. The IHV Extensions DLL must set 
     <i>dwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in 
     L2cmn.h.
     

The IHV Extensions DLL returns the general completion status of the post-association operation
     through the 
     <i>dwWin32Error</i> parameter. Typically, the IHV Extensions DLL sets 
     <i>dwReasonCode</i> to a value within the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
     L2_REASON_CODE_GROUP_SIZE-1).


### -param dwWin32Error [in]

The completion status of the post-association operation as defined by an error code within 
     Winerror.h. If the operation completes successfully, the IHV Extensions DLL must set 
     <i>dwWin32Error</i> to ERROR_SUCCESS.


## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.


## -remarks
The IHV Extensions DLL calls the 
    <i>Dot11ExtPostAssociateCompletion</i> function to do any of the following:

Complete the post-association operation initiated by a call to the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
      Dot11ExtIhvPerformPostAssociate</a> IHV Handler function.

After completing the post-association operation, indicate a change in the port state for the
      security session referenced by the 
      <i>hSecuritySessionID</i> parameter.

For example, if the authorization state of the port changes, the IHV Extensions DLL can notify the
      operating system by calling 
      <i>Dot11ExtPostAssociateCompletion</i>.

The IHV Extensions DLL must follow these guidelines when calling the 
    <b>Dot11ExtPostAssociateCompletion</b> function.

If the post-association operation completed successfully, the IHV Extensions DLL must set 
      <i>dwReasonCode</i> to one of the following:

L2_REASON_CODE_SUCCESS.

An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).

In this situation, the IHV Extensions DLL must set 
      <i>dwWin32Error</i> to ERROR_SUCCESS.

If the post-association operation completed with a failure, the IHV Extensions DLL must not set 
      <i>dwReasonCode</i> to L2_REASON_CODE_SUCCESS. Instead, the DLL must set 
      <i>dwReasonCode</i> to one of the following:

An appropriate L2_REASON_CODE_xxxx error value.

In this situation, the IHV Extensions DLL must not set 
      <i>dwWin32Error</i> to ERROR_SUCCESS. Instead, the DLL must set 
      <i>dwWin32Error</i> to an appropriate error code defined in 
      Winerror.h.

The IHV Extensions DLL must call 
      <b>Dot11ExtPostAssociateCompletion</b> to cancel all pending post-association operation whenever the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a> or 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a> IHV
      Handler functions are called. In this situation, the DLL must set the 
      <i>dwStatus</i> parameter to ERROR_CANCELLED.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wlanihv.h (include Wlanihv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.dot11_mac_address">DOT11_MAC_ADDRESS</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_POST_ASSOCIATE_COMPLETION callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

