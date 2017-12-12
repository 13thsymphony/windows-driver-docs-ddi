---
UID: NC.wlanihv.DOT11EXTIHV_PERFORM_PRE_ASSOCIATE
title: DOT11EXTIHV_PERFORM_PRE_ASSOCIATE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvperformpreassociate.htm
old-project: netvista
ms.assetid: 5bf7a1ce-bff0-481e-8053-584fb6319146
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _BINARY_CONTAINER, BINARY_CONTAINER, *PBINARY_CONTAINER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h, L2cmn.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvPerformPreAssociate
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

# DOT11EXTIHV_PERFORM_PRE_ASSOCIATE callback



## -description

## -prototype

````
DOT11EXTIHV_PERFORM_PRE_ASSOCIATE Dot11ExtIhvPerformPreAssociate;

DWORD APIENTRY Dot11ExtIhvPerformPreAssociate(
  _In_opt_ HANDLE                             hIhvExtAdapter,
  _In_opt_ HANDLE                             hConnectSession,
  _In_opt_ PDOT11EXT_IHV_PROFILE_PARAMS       pIhvProfileParams,
  _In_     PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_     PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile,
  _In_     PDOT11_BSS_LIST                    pConnectableBssid,
  _Out_    PDWORD                             pdwReasonCode
)
{ ... }
````


## -parameters

### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hConnectSession [in, optional]

The handle used by the operating system to reference the connection session with the basic service
     set (BSS) network.


### -param pIhvProfileParams [in, optional]

A pointer to a 
     <a href="netvista.dot11ext_ihv_profile_params">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure. This structure defines the attributes of the basic service
     set (BSS) network to which the profile extensions will be applied.


### -param pIhvConnProfile [in]

A pointer to a 
     <a href="netvista.dot11ext_ihv_connectivity_profile">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure that contains connectivity settings for the IHV
     profile.


### -param pIhvSecProfile [in]

A pointer to a 
     <a href="netvista.dot11ext_ihv_security_profile">
     DOT11EXT_IHV_SECURITY_PROFILE</a> structure that specifies security settings for the IHV
     profile.


### -param pConnectableBssid [in]

A pointer to a 
     <a href="netvista.dot11_bss_list">DOT11_BSS_LIST</a> structure, which contains one
     or more 802.11 Beacon or Probe Response frames for the service set identifier (SSID) of the BSS network
     with which the DLL will perform the pre-association operation.


### -param pdwReasonCode [out]

A pointer to a DWORD value, which provides additional information for the return value of the 
     <i>Dot11ExtIhvPerformPreAssociate</i> function. The IHV Extensions DLL must set *
     <i>pdwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in 
     L2cmn.h.


## -returns
If the IHV Extension DLL can initiate the pre-association operation, it must complete the operation
      asynchronously. In this situation, the function returns ERROR_SUCCESS.

If the IHV Extensions DLL cannot initiate the pre-association operation, it returns an error code
      defined in 
      <i>Winerror.h</i>.


## -remarks
The operating system calls the 
    <i>Dot11ExtIhvPerformPreAssociate</i> function to initiate a pre-association operation with the IHV
    Extensions DLL. The operating system initiates this operation before it initiates a connection operation
    with a basic service set (BSS) network through the WLAN adapter. For more information about the
    connection operation, see 
    <a href="netvista.connection_operations">Connection Operations</a>.

The pre-association operation must be completed asynchronously from the call to 
    <i>Dot11ExtIhvPerformPreAssociate</i>. After the pre-association operation completes, the IHV Extensions
    DLL must call 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
    Dot11ExtPreAssociateCompletion</a>.

When the 
    <i>Dot11ExtIhvPerformPreAssociate</i> function is called, the IHV Extensions DLL must follow these
    guidelines.

If the IHV Extensions DLL can initiate the pre-association operation, the 
      <i>Dot11ExtIhvPerformPreAssociate</i> function must return ERROR_SUCCESS and complete the operation
      asynchronously.

The IHV Extensions DLL provides more information regarding the initiation of the pre-association
      operation through the 
      <i>pdwReasonCode</i> parameter. The DLL must set *
      <i>pdwReasonCode</i> to one of the following:

L2_REASON_CODE_SUCCESS, if the pre-association operation can initiated successfully.

An appropriate L2_REASON_CODE_xxxx error value, if the pre-association operation could not be
        initiated.

An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1), regardless of whether the pre-association operation could be initiated
        or not.

For more information about the pre-association operation, see 
    <a href="netvista.pre_association_operations">Pre-Association Operation</a>.


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
<dt>Wlanihv.h (include Wlanihv.h or L2cmn.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.dot11_bss_list">DOT11_BSS_LIST</a>
</dt>
<dt>
<a href="netvista.dot11ext_ihv_connectivity_profile">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>
</dt>
<dt>
<a href="netvista.dot11ext_ihv_profile_params">DOT11EXT_IHV_PROFILE_PARAMS</a>
</dt>
<dt>
<a href="netvista.dot11ext_ihv_security_profile">DOT11EXT_IHV_SECURITY_PROFILE</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
   Dot11ExtPreAssociateCompletion</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_extensibility_functions">Native 802.11 IHV
   Extensibility Functions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569122">OID_DOT11_CONNECT_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_PERFORM_PRE_ASSOCIATE callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

