---
UID: NE:ufs.UFS_ATTRIBUTES_DESCRIPTOR
title: UFS_ATTRIBUTES_DESCRIPTOR
author: windows-driver-content
description: UFS_ATTRIBUTES_DESCRIPTOR describes the different types of attributes used by Universal Flash Storage (UFS) descriptors.
old-location: storage\ufs_attributes_descriptor.htm
old-project: storage
ms.assetid: 695D8FE9-FADB-488F-A5F7-7715EAD48DD6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: UFS_wContextConf, UFS_wExceptionEventControl, UFS_bActiveICCLevel, ufs/UFS_Reserved01, UFS_dDynCapNeeded, UFS_Reserved02, UFS_bDeviceFFUStatus, UFS_Obsolete, ufs/UFS_Reserved02, UFS_Reserved03, UFS_bRefClkFreq, ufs/UFS_bActiveICCLevel, ufs/UFS_Reserved03, ufs/UFS_bConfigDescrLock, UFS_wExceptionEventStatus, ufs/UFS_dSecondsPassed, UFS_dSecondsPassed, ufs/UFS_bPurgeStatus, ufs/UFS_wExceptionEventControl, ufs/UFS_bCurrentPowerMode, UFS_bOutOfOrderDataEn, ufs/UFS_Obsolete, ufs/UFS_dPSADataSize, UFS_bConfigDescrLock, UFS_bMaxDataInSize, UFS_ATTRIBUTES_DESCRIPTOR, UFS_bBackgroundOpStatus, ufs/UFS_bBackgroundOpStatus, ufs/UFS_bMaxNumOfRTT, ufs/UFS_bDeviceFFUStatus, ufs/UFS_bMaxDataInSize, ufs/UFS_ATTRIBUTES_DESCRIPTOR, ufs/UFS_bBootLunEn, ufs/UFS_wExceptionEventStatus, UFS_bMaxNumOfRTT, UFS_bPurgeStatus, UFS_bPSAState, storage.ufs_attributes_descriptor, UFS_dPSADataSize, ufs/UFS_dDynCapNeeded, UFS_bBootLunEn, ufs/UFS_bPSAState, ufs/UFS_bOutOfOrderDataEn, ufs/UFS_bRefClkFreq, UFS_Reserved01, ufs/UFS_wContextConf, UFS_bCurrentPowerMode, UFS_bMaxDataOutSize, ufs/UFS_bMaxDataOutSize, UFS_ATTRIBUTES_DESCRIPTOR enumeration [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
-	Ufs.h
apiname:
-	UFS_ATTRIBUTES_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_ATTRIBUTES_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_ATTRIBUTES_DESCRIPTOR Enumeration
<b>UFS_ATTRIBUTES_DESCRIPTOR</b> describes the different types of attributes used by Universal Flash Storage (UFS) descriptors.

## Syntax
````
typedef enum _UFS_ATTRIBUTES_DESCRIPTOR { 
  UFS_bBootLunEn              = 0,
  UFS_Reserved01,
  UFS_bCurrentPowerMode,
  UFS_bActiveICCLevel,
  UFS_bOutOfOrderDataEn,
  UFS_bBackgroundOpStatus,
  UFS_bPurgeStatus,
  UFS_bMaxDataInSize,
  UFS_bMaxDataOutSize,
  UFS_dDynCapNeeded,
  UFS_bRefClkFreq,
  UFS_bConfigDescrLock,
  UFS_bMaxNumOfRTT,
  UFS_wExceptionEventControl,
  UFS_wExceptionEventStatus,
  UFS_dSecondsPassed,
  UFS_wContextConf,
  UFS_Obsolete,
  UFS_Reserved02,
  UFS_Reserved03,
  UFS_bDeviceFFUStatus,
  UFS_bPSAState,
  UFS_dPSADataSize
} UFS_ATTRIBUTES_DESCRIPTOR;
````

## Constants

<table>
            
                <tr>
                    <td>UFS_bActiveICCLevel</td>
                    <td>Specifies the maximum
current consumption allowed during
Active Mode. Value ranges from 0x00 to 0x0F.</td>
                </tr>
            
                <tr>
                    <td>UFS_bBackgroundOpStatus</td>
                    <td>Specifies if the device has a need for background operations. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Device requires no background operations.</td>
</tr>
<tr>
<td>0x01</td>
<td>Device has a non-critical need of background operations.</td>
</tr>
<tr>
<td>0x02</td>
<td>Device has a performance impacted-based need of background operations.</td>
</tr>
<tr>
<td>0x03</td>
<td>Device has a critical need of background operations. </td>
</tr>
</table></td>
                </tr>
            
                <tr>
                    <td>UFS_bBootLunEn</td>
                    <td>Indicates if the Boot Logical Unit Number(LUN) is enabled.</td>
                </tr>
            
                <tr>
                    <td>UFS_bConfigDescrLock</td>
                    <td>Specifies if the configuration descriptor is locked.</td>
                </tr>
            
                <tr>
                    <td>UFS_bCurrentPowerMode</td>
                    <td>Indicates the current power mode. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Idle power mode.</td>
</tr>
<tr>
<td>0x10</td>
<td>Pre-Active power mode.</td>
</tr>
<tr>
<td>0x11</td>
<td>Active power mode.</td>
</tr>
<tr>
<td>0x20</td>
<td>Pre-Sleep power mode.</td>
</tr>
<tr>
<td>0x22</td>
<td>Universal Flash Storage (UFS)-Sleep power mode.</td>
</tr>
<tr>
<td>0x30</td>
<td>40% to 50% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x33</td>
<td>50% to 60% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table></td>
                </tr>
            
                <tr>
                    <td>UFS_bDeviceFFUStatus</td>
                    <td>Specifies the Device Field Firmware Update (FFU) status.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>No information on the FFU status.</td>
</tr>
<tr>
<td>0x01</td>
<td>Successful microcode update.</td>
</tr>
<tr>
<td>0x02</td>
<td>Microcode corruption error.</td>
</tr>
<tr>
<td>0x03</td>
<td>Internal error.</td>
</tr>
<tr>
<td>0x04</td>
<td>Microcode version mismatch.</td>
</tr>
<tr>
<td>0x05 to 0xFE </td>
<td>Reserved.</td>
</tr>
<tr>
<td>0xFF</td>
<td>General Error.</td>
</tr>
</table></td>
                </tr>
            
                <tr>
                    <td>UFS_bMaxDataInSize</td>
                    <td>Specifies the maximum data size in a DATA IN UFS Protocol Information Units (UPIU). This parameter can be written by the
host only when all logical unit task queues are
empty.</td>
                </tr>
            
                <tr>
                    <td>UFS_bMaxDataOutSize</td>
                    <td>Specifies the maximum data-out size. This parameter can be written by the
host only when all logical unit task queues are
empty.</td>
                </tr>
            
                <tr>
                    <td>UFS_bMaxNumOfRTT</td>
                    <td>Defines the current maximum number of outstanding READY TO TRANSFER UPIU’s (RTT's) that are
allowed. This value can be set by the host.</td>
                </tr>
            
                <tr>
                    <td>UFS_bOutOfOrderDataEn</td>
                    <td>Specifies if out-of-order data transfer is
enabled</td>
                </tr>
            
                <tr>
                    <td>UFS_bPSAState</td>
                    <td>Specifies the current Product State Awareness (PSA) State.

<table>
<tr>
<th>Value</th>
<th>State</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Off</td>
<td>PSA feature is off.</td>
</tr>
<tr>
<td>0x01</td>
<td>Pre-solder</td>
<td>PSA feature is on and the device is in a pre-soldering state.</td>
</tr>
<tr>
<td>0x02</td>
<td>Loading Complete</td>
<td>The PSA feature
is on. The host will set to this
value after the host finished
writing data during pre-soldering
state.</td>
</tr>
<tr>
<td>0x03</td>
<td>Soldered</td>
<td>PSA feature is no
longer available. Set by the
Device to indicate it is in a post-soldering state. This attribute
is locked after it is in
‘Soldered’ state.</td>
</tr>
</table></td>
                </tr>
            
                <tr>
                    <td>UFS_bPurgeStatus</td>
                    <td>Specifies the current purge operation's status.</td>
                </tr>
            
                <tr>
                    <td>UFS_bRefClkFreq</td>
                    <td>Specifies the reference clock frequency value.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>19.2 MHz</td>
</tr>
<tr>
<td>0x01</td>
<td>26 MHz</td>
</tr>
<tr>
<td>0x02</td>
<td>38.4 MHz</td>
</tr>
<tr>
<td>0x03</td>
<td>52 MHz</td>
</tr>
</table></td>
                </tr>
            
                <tr>
                    <td>UFS_dDynCapNeeded</td>
                    <td>Specifies the dynamic capacity need.</td>
                </tr>
            
                <tr>
                    <td>UFS_dPSADataSize</td>
                    <td>Specifies the amount of data that the host plans
to load to all logical units with
<b>bPSASensitive</b> set to 1.</td>
                </tr>
            
                <tr>
                    <td>UFS_dSecondsPassed</td>
                    <td>Specifies the time passed in seconds.</td>
                </tr>
            
                <tr>
                    <td>UFS_Obsolete</td>
                    <td>Obselete</td>
                </tr>
            
                <tr>
                    <td>UFS_Reserved01</td>
                    <td>Reserved for future use.</td>
                </tr>
            
                <tr>
                    <td>UFS_Reserved02</td>
                    <td>Reserved for future use.</td>
                </tr>
            
                <tr>
                    <td>UFS_Reserved03</td>
                    <td>Reserved for future use.</td>
                </tr>
            
                <tr>
                    <td>UFS_wContextConf</td>
                    <td>Specifies the context attribute.</td>
                </tr>
            
                <tr>
                    <td>UFS_wExceptionEventControl</td>
                    <td>Specifies the Exception Event Controller. <b>UFS_wExceptionEventControl</b> enables the setting of the
<b>EVENT_ALERT</b> bit in the Device
Information field, which is contained in
the RESPONSE UPIU.</td>
                </tr>
            
                <tr>
                    <td>UFS_wExceptionEventStatus</td>
                    <td>Specifies a bitmap of each exception event status.A bit will be set only if the
relevant event has occurred
(regardless of the
<b>UFS_wExceptionEventControl</b> status). Contains the following bits:

<table>
<tr>
<th>Bit</th>
<th>Value</th>
</tr>
<tr>
<td>0</td>
<td>DYNCAP_NEEDED</td>
</tr>
<tr>
<td>1</td>
<td>SYSPOOL_EXHAUSTED</td>
</tr>
<tr>
<td>2</td>
<td>URGENT_BKOPS</td>
</tr>
<tr>
<td>3 to 15</td>
<td>Reserved.</td>
</tr>
</table></td>
                </tr>
</table>

## Remarks

<b>UFS_bCurrentPowerMode</b> is the only attribute the device is required to return in any power mode. If the device
is not in Active power mode or Idle power mode, a <b>QUERY REQUEST UPIU</b> to access descriptors, flags, or attributes other than <b>bCurrentPowerMode</b> may fail.

<b>UFS_bDeviceFFUStatu</b>s value is kept after power cycle, hardware reset or any other type of reset. This attribute may change value when a
microcode activation event occurs.

<b>UFS_bMaxDataInSize</b> is equal to <b>bMaxInBufferSize</b> when a UFS device is shipped.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ufs.h |

## See Also

<a href="..\ufs\ns-ufs-ufs_geometry_descriptor.md">UFS_GEOMETRY_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_device_health_descriptor.md">UFS_DEVICE_HEALTH_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_power_descriptor.md">UFS_POWER_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_device_descriptor.md">UFS_DEVICE_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_unit_descriptor.md">UFS_UNIT_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_rpmb_unit_descriptor.md">UFS_RPMB_UNIT_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_unit_config_descriptor.md">UFS_UNIT_CONFIG_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_config_descriptor.md">UFS_CONFIG_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_interconnect_descriptor.md">UFS_INTERCONNECT_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-_ufs_string_descriptor.md">UFS_STRING_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20UFS_ATTRIBUTES_DESCRIPTOR enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>