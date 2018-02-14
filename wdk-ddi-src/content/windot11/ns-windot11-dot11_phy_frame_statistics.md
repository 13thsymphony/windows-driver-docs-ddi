---
UID: NS:windot11.DOT11_PHY_FRAME_STATISTICS
title: DOT11_PHY_FRAME_STATISTICS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_frame_statistics.htm
old-project: netvista
ms.assetid: 2adf102b-52aa-40e4-b3de-9189803339bf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_PHY_FRAME_STATISTICS structure [Network Drivers Starting with Windows Vista], PDOT11_PHY_FRAME_STATISTICS structure pointer [Network Drivers Starting with Windows Vista], windot11/PDOT11_PHY_FRAME_STATISTICS, *PDOT11_PHY_FRAME_STATISTICS, windot11/DOT11_PHY_FRAME_STATISTICS, DOT11_PHY_FRAME_STATISTICS, PDOT11_PHY_FRAME_STATISTICS, Native_802.11_data_types_e7446fc8-9a7c-41c5-bf90-7988dfddc950.xml, netvista.dot11_phy_frame_statistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_PHY_FRAME_STATISTICS
product: Windows
targetos: Windows
req.typenames: DOT11_PHY_FRAME_STATISTICS, *PDOT11_PHY_FRAME_STATISTICS
req.product: Windows 10 or later.
---

# DOT11_PHY_FRAME_STATISTICS structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PHY_FRAME_STATISTICS structure records statistical counters for the IEEE physical (PHY)
  layer of the 802.11 station.

## Syntax
````
typedef struct DOT11_PHY_FRAME_STATISTICS {
  ULONGLONG ullTransmittedFrameCount;
  ULONGLONG ullMulticastTransmittedFrameCount;
  ULONGLONG ullFailedCount;
  ULONGLONG ullRetryCount;
  ULONGLONG ullMultipleRetryCount;
  ULONGLONG ullMaxTXLifetimeExceededCount;
  ULONGLONG ullTransmittedFragmentCount;
  ULONGLONG ullRTSSuccessCount;
  ULONGLONG ullRTSFailureCount;
  ULONGLONG ullACKFailureCount;
  ULONGLONG ullReceivedFrameCount;
  ULONGLONG ullMulticastReceivedFrameCount;
  ULONGLONG ullPromiscuousReceivedFrameCount;
  ULONGLONG ullMaxRXLifetimeExceededCount;
  ULONGLONG ullFrameDuplicateCount;
  ULONGLONG ullReceivedFragmentCount;
  ULONGLONG ullPromiscuousReceivedFragmentCount;
  ULONGLONG ullFCSErrorCount;
} DOT11_PHY_FRAME_STATISTICS, *PDOT11_PHY_FRAME_STATISTICS;
````

## Members


`ullACKFailureCount`

The number of times that the 802.11 station expected and did not receive an Acknowledgement (ACK)
     frame.

`ullFailedCount`

The number of MSDU packets and MMPDU frames that the 802.11 station failed to transmit after
     exceeding the retry limits defined by the 802.11 IEEE 
     <b>dot11ShortRetryLimit</b> or 
     <b>dot11LongRetryLimit</b> MIB counters. For more information about these MIB counters, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569415">OID_DOT11_SHORT_RETRY_LIMIT</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569380">OID_DOT11_LONG_RETRY_LIMIT</a>.

`ullFCSErrorCount`

The number of MPDU frames that the 802.11 station received with FCS errors.

`ullFrameDuplicateCount`

The number of duplicate MPDU frames that the 802.11 station received. The 802.11 station
     determines duplicate frames through the Sequence Control field of the 802.11 MAC header.

`ullMaxRXLifetimeExceededCount`

The number if MSDU packets and MMPDU frames that the 802.11 station discarded because of a timeout
     as defined by the IEEE 802.11 
     <b>dot11MaxReceiveLifetime</b> MIB object. For more information about this MIB object, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-max-receive-lifetime">
     OID_DOT11_MAX_RECEIVE_LIFETIME</a>.

`ullMaxTXLifetimeExceededCount`

The number of MSDU packets and MMPDU frames that the 802.11 station failed to transmit because of
     a timeout as defined by the IEEE 802.11 
     <b>dot11MaxTransmitMSDULifetime</b> MIB object. For more information about this MIB object, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-max-transmit-msdu-lifetime">
     OID_DOT11_MAX_TRANSMIT_MSDU_LIFETIME</a>.

`ullMulticastReceivedFrameCount`

The number of multicast or broadcast MSDU packets and MMPDU frames that the 802.11 station has
     successfully received.
     

For MSDU packets, the miniport driver must increment this counter for each packet whose MPDU
     fragments were received and passed FCS verification and replay detection. The miniport driver must
     increment this member regardless of whether the received MSDU packet or MPDU fragment fail MAC-layer
     cipher decryption.

This counter is optional. If the NIC does not support this counter, the miniport driver should set
     this member to DOT11_STATISTICS_UNKNOWN.

`ullMulticastTransmittedFrameCount`

The number of multicast or broadcast MSDU packets and MMPDU frames that the IEEE PHY layer of the
     802.11 station has successfully transmitted.

`ullMultipleRetryCount`

The number of MSDU packets and MMPDU frames that the 802.11 station successfully transmitted after
     more than one retransmission attempt. 
     

For MSDU packets, the miniport driver must increment this counter for each packet that was
     transmitted successfully after one or more of its MPDU fragments required retransmission.

`ullPromiscuousReceivedFragmentCount`

The number of MPDU frames received by the 802.11 station for MSDU packets or MMPDU frames when a
     promiscuous packet filter was enabled. For more information about packet filters, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>.
     

If a promiscuous packet filter is enabled, the miniport driver must only increment this counter for
     received MPDU frames that would have been rejected if the filter was not enabled. The driver must not
     increment this counter for:

<ul>
<li>
Unicast MPDU frames with a destination MAC address that matches the 802.11 station's MAC
       address.

</li>
<li>
Multicast or broadcast MPDU frames with a destination MAC address that matches an entry in the
       multicast address list of the 802.11 station. For more information about the multicast address list,
       see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569388">OID_DOT11_MULTICAST_LIST</a>.

</li>
</ul>

`ullPromiscuousReceivedFrameCount`

The number of MSDU packets or MMPDU frames received by the 802.11 station when a promiscuous
     packet filter is enabled. For more information about packet filters, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>.
     

If a promiscuous packet filter is enabled, the miniport driver must only increment this counter for
     received MSDU packets or MMPDU frames that would have been rejected if the filter was not enabled. The
     driver must not increment this counter for:

<ul>
<li>
Unicast MSDU packets or MMPDU frames with a destination MAC address that matches the 802.11
       station's MAC address.

</li>
<li>
Multicast or broadcast MSDU packets or MMPDU frames with a destination MAC address that matches an
       entry in the multicast address list of the 802.11 station. For more information about the multicast
       address list, see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569388">OID_DOT11_MULTICAST_LIST</a>.

</li>
</ul>

`ullReceivedFragmentCount`

The number of MPDU frames received by the 802.11 station for MSDU packets or MMPDU frames.

`ullReceivedFrameCount`

The total number of MSDU packets and MMPDU frames that the 802.11 station has successfully
     received.
     

For MSDU packets, the miniport driver must increment this counter for each packet whose MPDU
     fragments were received and passed frame check sequence (FCS) verification and replay detection. The
     miniport driver must increment this member regardless of whether the received MSDU packet or MPDU
     fragment fail MAC-layer cipher decryption.

This counter is optional. If the NIC does not support this counter, the miniport driver should set
     this member to DOT11_STATISTICS_UNKNOWN.

`ullRetryCount`

The number of MSDU packets and MMPDU frames that the 802.11 station successfully transmitted after
     one or more attempts.

`ullRTSFailureCount`

The number of times that the 802.11 station did not receive a CTS frame in response to an RTS
     frame.

`ullRTSSuccessCount`

The number of times that the 802.11 station received a Clear To Send (CTS) frame in response to a
     Request To Send (RTS) frame.

`ullTransmittedFragmentCount`

The number of MPDU frames that the 802.11 station transmitted and acknowledged through a received
     802.11 ACK frame.

`ullTransmittedFrameCount`

The number of MSDU packets and MMPDU frames that the IEEE PHY layer of the 802.11 station has
     successfully transmitted.

## Remarks
The members of this structure are used to record PHY-level statistics for:

<ul>
<li>
802.11 MSDU packets.

</li>
<li>
802.11 MMPDU frames.

</li>
<li>
802.11 MPDU frames. MPDU frame counters must include all MPDU fragments sent for an MSDU packet or
      MMPDU frame

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | windot11.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/e6bd2abf-faa2-463f-91df-a15924afae96">Native 802.11 Statistics</a>



<a href="..\windot11\ns-windot11-dot11_statistics.md">DOT11_STATISTICS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/extensible-station-phy-statistics">Extensible Station PHY
   Statistics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569420">OID_DOT11_STATISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PHY_FRAME_STATISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>