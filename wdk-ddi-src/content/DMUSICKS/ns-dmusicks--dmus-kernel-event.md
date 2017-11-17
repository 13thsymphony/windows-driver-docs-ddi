---
UID: NS.dmusicks._DMUS_KERNEL_EVENT
title: DMUS_KERNEL_EVENT
author: windows-driver-content
description: The DMUS_KERNEL_EVENT structure is used to package time-stamped music events.
old-location: audio\dmus_kernel_event.htm
ms.assetid: 652f64e2-310b-46c9-8b00-c827a7475b07
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: audio
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DMUS_KERNEL_EVENT
req.alt-loc: dmusicks.h
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
ms.keywords: DMUS_KERNEL_EVENT, DMUS_KERNEL_EVENT, *PDMUS_KERNEL_EVENT
req.iface: ISynthSinkDMus
---

# DMUS_KERNEL_EVENT structure



## -description
<p>The DMUS_KERNEL_EVENT structure is used to package time-stamped music events.</p>


## -syntax

````
typedef struct _DMUS_KERNEL_EVENT {
  BYTE               bReserved;
  BYTE               cbStruct;
  USHORT             cbEvent;
  USHORT             usChannelGroup;
  USHORT             usFlags;
  REFERENCE_TIME     ullPresTime100ns;
  ULONGLONG          ullBytePosition;
  _DMUS_KERNEL_EVENT *pNextEvt;
  union {
    BYTE               abData[sizeof(PBYTE)];
    PBYTE              pbData;
    _DMUS_KERNEL_EVENT *pPackageEvt;
  } uData;
} DMUS_KERNEL_EVENT, *PDMUS_KERNEL_EVENT;
````


## -struct-fields
<dl>

### -field <b>bReserved</b>

<dd>
<p>
      Miniport drivers should not modify this member. Reserved for future use. Do not use.</p>
</dd>

### -field <b>cbStruct</b>

<dd>
<p>
      Miniport drivers should not modify this member.
       This member specifies the size of the DMUS_KERNEL_EVENT structure itself and could change in the future.</p>
</dd>

### -field <b>cbEvent</b>

<dd>
<p>Specifies the unrounded number of event bytes referred to by <b>uData</b>.</p>
</dd>

### -field <b>usChannelGroup</b>

<dd>
<p>Specifies which channel group (set of 16 MIDI channels) receives or originated this event. This is unique only within the target MIDI device (miniport driver).</p>
</dd>

### -field <b>usFlags</b>

<dd>
<p>Specifies whether an event is a package and whether this event concludes the message. A package encapsulates a list of events that should be dealt with atomically. This member is a bitfield that can be set to the bitwise OR of one or more of the following flag bits:</p>
<p></p>
<dl>

### -field <a id="DMUS_KEF_EVENT_COMPLETE__zero_"></a><a id="dmus_kef_event_complete__zero_"></a><a id="DMUS_KEF_EVENT_COMPLETE__ZERO_"></a>DMUS_KEF_EVENT_COMPLETE (zero)

<dd>
<p>Specifies messages in which the entire message is contained either in <b>uData.abData</b> or in the buffer pointed to by <b>uData.pbData</b>. The former includes all short messages, and potentially includes very brief SysEx messages (see Microsoft Windows SDK documentation) as well. Keep in mind that <b>sizeof</b>(PBYTE) can be 8 instead of 4 on 64-bit versions of Windows.</p>
</dd>

### -field <a id="DMUS_KEF_EVENT_INCOMPLETE"></a><a id="dmus_kef_event_incomplete"></a>DMUS_KEF_EVENT_INCOMPLETE

<dd>
<p>Specifies that this event is an incomplete package or SysEx message (see Windows SDK documentation). This flag specifies that the message continues beyond this event. During MIDI capture, the miniport driver can send "uncooked" MIDI events (raw MIDI input data) to the capture sink by specifying this flag.</p>
</dd>

### -field <a id="DMUS_KEF_PACKAGE_EVENT"></a><a id="dmus_kef_package_event"></a>DMUS_KEF_PACKAGE_EVENT

<dd>
<p>Specifies that this event is a package. The <b>uData.pPackageEvt</b> field contains a pointer to a chain of events which should be dealt with atomically.</p>
</dd>
</dl>
</dd>

### -field <b>ullPresTime100ns</b>

<dd>
<p>Specifies the presentation time for this event. This 64-bit value is expressed in 100-nanosecond units. The master clock should be used to evaluate this presentation time.</p>
</dd>

### -field <b>ullBytePosition</b>

<dd>
<p>8 16</p>
</dd>

### -field <b>pNextEvt</b>

<dd>
<p>Pointer to the next event in the list, or <b>NULL</b> if no event follows. This facilitates passing chains of identically time-stamped messages to the miniport driver. Additionally, hardware that does its own mixing can receive or transmit groups of messages at one time.</p>
</dd>

### -field <b>uData</b>

<dd>
<dl>

### -field <b>abData</b>

<dd>
<p>A byte array containing <b>cbEvent</b> bytes of event data. The event data are typically MIDI status and data bytes. This member of <b>uData</b> is used if <b>cbEvent</b> is less than or equal to <b>sizeof</b>(PBYTE).</p>
</dd>

### -field <b>pbData</b>

<dd>
<p>Pointer to a buffer containing <b>cbEvent</b> bytes of event data. The event data are typically MIDI status and data bytes. This member of <b>uData</b> is used if <b>uFlags</b> is set to DMUS_KEF_EVENT_COMPLETE and <b>cbEvent</b> is greater than <b>sizeof</b>(PBYTE).</p>
</dd>

### -field <b>pPackageEvt</b>

<dd>
<p>Pointer to a chain of events, which is in the form of a linked list of DMUS_KERNEL_EVENT structures. The event data typically consist of MIDI status and data bytes. The events in the list are to be handled together. This member of <b>uData</b> is used if <b>uFlags</b> is set to DMUS_KEF_PACKAGE_EVENT.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The DMUS_KERNEL_EVENT structure is used by WDM audio drivers that provide kernel streaming support for DirectMusic.</p>

<p>While capturing a MIDI stream, the DMus port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536494">IAllocatorMXF::GetMessage</a> method to retrieve DMUS_KERNEL_EVENT structures to hold the captured data. While rendering a MIDI stream, the port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> method to discard DMUS_KERNEL_EVENT structures as it finishes reading them. For more information, see <a href="NULL">MIDI Transport</a>.</p>

<p>In the case of MIDI capture, the DMUS_KERNEL_EVENT structure can be packaged with single, multiple, or fragmentary MIDI messages. The <b>usFlags</b> member should be set to DMUS_KEF_EVENT_INCOMPLETE unless it is a single complete MIDI message. This structure also contains:</p>

<p>A time stamp relative to the master clock (ullPresTime100Ns)</p>

<p>Extended channel information (usChannelGroup)</p>

<p>Mapping to the correct DLS instrument is implicit in the triplet of</p>

<p>&lt;<i>pin</i>, <i>channel_group</i>, <i>channel</i>&gt;</p>

<p>Presentation time does not advance during the states KSSTATE_PAUSE and KSSTATE_STOP, and is reset during KSSTATE_STOP. For more information, see <a href="NULL">KS Clocks</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dmusicks.h (include Dmusicks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536494">IAllocatorMXF::GetMessage</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DMUS_KERNEL_EVENT structure%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
