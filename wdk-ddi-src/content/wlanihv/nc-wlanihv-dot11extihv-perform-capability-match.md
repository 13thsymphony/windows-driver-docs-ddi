---
UID: NC.wlanihv.DOT11EXTIHV_PERFORM_CAPABILITY_MATCH
title: DOT11EXTIHV_PERFORM_CAPABILITY_MATCH
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvperformcapabilitymatch.htm
ms.assetid: c49b23c0-4707-4626-8035-a83ccf7638eb
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: wlanihv.h
req.include-header: Wlanihv.h, Winclient.h, L2cmn.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvPerformCapabilityMatch
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
ms.keywords: PrintPropertyValue, PrintPropertyValue
req.iface: 
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PERFORM_CAPABILITY_MATCH callback



## -description

## -prototype

````
DOT11EXTIHV_PERFORM_CAPABILITY_MATCH Dot11ExtIhvPerformCapabilityMatch;

DWORD APIENTRY Dot11ExtIhvPerformCapabilityMatch(
  _In_opt_ HANDLE                             hIhvExtAdapter,
  _In_opt_ PDOT11EXT_IHV_PROFILE_PARAMS       pIhvProfileParams,
  _In_     PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_     PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile,
  _In_opt_ PDOT11_BSS_LIST                    pConnectableBssid,
  _Out_    PDWORD                             pdwReasonCode
)
{ ... }
````


## -parameters
<dl>

### -param <i>hIhvExtAdapter</i> [in, optional]

<dd>
<p>The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the 
     <a href="https://msdn.microsoft.com/96dc1718-ee35-440a-94e8-eba4a41c9559">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.</p>
</dd>

### -param <i>pIhvProfileParams</i> [in, optional]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/9bf4b27c-3cf0-45a0-9e56-b01ad1ba6b19">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure. This structure defines the attributes of the basic service
     set (BSS) network to which the profile extensions will be applied.</p>
</dd>

### -param <i>pIhvConnProfile</i> [in]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/56ef9b59-5dbb-4720-bae1-7af6d9dbc110">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure that contains connectivity settings for the IHV
     profile.</p>
</dd>

### -param <i>pIhvSecProfile</i> [in]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/cbfeace3-6492-4011-9ca8-c40ba4f47d22">
     DOT11EXT_IHV_SECURITY_PROFILE</a> structure that contains security settings for the IHV
     profile.</p>
</dd>

### -param <i>pConnectableBssid</i> [in, optional]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547668">DOT11_BSS_LIST</a> structure, which contains one
     or more 802.11 Beacon or Probe Response frames received from a BSS network. This list is derived from
     the results of the last scan operation performed by the WLAN adapter. For more information about the
     scan operation, see 
     <a href="NULL">Native 802.11 Scan Operations</a>.
     </p>
<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div>
<div> </div>
</dd>

### -param <i>pdwReasonCode</i> [out]

<dd>
<p>A pointer to a DWORD value, which provides additional information for the return value of the 
     <i>Dot11ExtIhvPerformCapabilityMatch</i> function. The IHV Extensions DLL must set *
     <i>pdwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in 
     L2cmn.h.</p>
</dd>
</dl>

## -returns
<p>If all of the entries in the list of 802.11 Beacon and Probe Response frames support the
     connectivity and security attributes defined in the profile fragments, the function returns
     ERROR_SUCCESS. Otherwise, it returns an error code defined in 
     Winerror.h.</p>

## -remarks
<p>After the WLAN adapter has completed a scan operation to detect the BSS networks within range, the
    operating system might call the 
    <i>Dot11ExtIhvPerformCapabilityMatch</i> function to determine whether any of the detected BSS networks
    matches the connectivity or security profile extensions defined by the IHV.</p>

<p>When the 
    <i>Dot11ExtIhvPerformCapabilityMatch</i> function is called, the IHV Extensions DLL must follow these
    guidelines.</p>

<p>If the IHV Extensions DLL finds at least one IEEE 802.11 Beacon or Probe Response frame that matches
      the profile fragments, it must set *
      <i>pdwReasonCode</i> to one of the following:</p>

<p>L2_REASON_CODE_SUCCESS.</p>

<p>An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).</p>

<p>In this situation, the 
      <i>Dot11ExtIhvPerformCapabilityMatch</i> function must return ERROR_SUCCESS.</p>

<p>If the IHV Extensions DLL does not find an IEEE 802.11 Beacon or Probe Response frame that matches
      the profile fragments, it must not set 
      <i>*pdwReasonCode</i> to L2_REASON_CODE_SUCCESS. Instead, the DLL must set *
      <i>pdwReasonCode</i> to one of the following:</p>

<p>An appropriate L2_REASON_CODE_xxxx error value.</p>

<p>An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).</p>

<p>In this situation, the 
      <i>Dot11ExtIhvPerformCapabilityMatch</i> function must not return ERROR_SUCCESS.</p>

<p>For more information about the Native 802.11 XML schema, refer to the Microsoft Windows SDK
    documentation.</p>

<p>After the WLAN adapter has completed a scan operation to detect the BSS networks within range, the
    operating system might call the 
    <i>Dot11ExtIhvPerformCapabilityMatch</i> function to determine whether any of the detected BSS networks
    matches the connectivity or security profile extensions defined by the IHV.</p>

<p>When the 
    <i>Dot11ExtIhvPerformCapabilityMatch</i> function is called, the IHV Extensions DLL must follow these
    guidelines.</p>

<p>If the IHV Extensions DLL finds at least one IEEE 802.11 Beacon or Probe Response frame that matches
      the profile fragments, it must set *
      <i>pdwReasonCode</i> to one of the following:</p>

<p>L2_REASON_CODE_SUCCESS.</p>

<p>An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).</p>

<p>In this situation, the 
      <i>Dot11ExtIhvPerformCapabilityMatch</i> function must return ERROR_SUCCESS.</p>

<p>If the IHV Extensions DLL does not find an IEEE 802.11 Beacon or Probe Response frame that matches
      the profile fragments, it must not set 
      <i>*pdwReasonCode</i> to L2_REASON_CODE_SUCCESS. Instead, the DLL must set *
      <i>pdwReasonCode</i> to one of the following:</p>

<p>An appropriate L2_REASON_CODE_xxxx error value.</p>

<p>An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).</p>

<p>In this situation, the 
      <i>Dot11ExtIhvPerformCapabilityMatch</i> function must not return ERROR_SUCCESS.</p>

<p>For more information about the Native 802.11 XML schema, refer to the Microsoft Windows SDK
    documentation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wlanihv.h (include Wlanihv.h, Winclient.h, or L2cmn.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547668">DOT11_BSS_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/56ef9b59-5dbb-4720-bae1-7af6d9dbc110">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547630">DOT11EXT_IHV_PROFILE_PARAMS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547632">DOT11EXT_IHV_SECURITY_PROFILE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/96dc1718-ee35-440a-94e8-eba4a41c9559">Dot11ExtIhvInitAdapter</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_PERFORM_CAPABILITY_MATCH callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
