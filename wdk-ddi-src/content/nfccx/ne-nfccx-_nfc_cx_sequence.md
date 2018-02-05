---
UID : NE:nfccx._NFC_CX_SEQUENCE
title : "_NFC_CX_SEQUENCE"
author : windows-driver-content
description : The NFC_CX_SEQUENCE enumeration specifies sequences.
old-location : nfpdrivers\nfc_cx_sequence.htm
old-project : nfpdrivers
ms.assetid : 752451F9-74FC-48A8-B9B8-2CBD381B91D9
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : SequencePreRfDiscStart, SequencePreNfceeDisc, SequencePreShutdown, SequencePreRecovery, _NFC_CX_SEQUENCE, nfccx/SequencePreRfDiscStart, nfccx/SequenceInitComplete, nfccx/SequencePreInit, NFC_CX_SEQUENCE, SequenceRecoveryComplete, SequenceRfDiscStartComplete, nfccx/SequenceRfDiscStopComplete, PNFC_CX_SEQUENCE, nfccx/NFC_CX_SEQUENCE, nfpdrivers.nfc_cx_sequence, SequenceInitComplete, SequencePreRfDiscStop, *PNFC_CX_SEQUENCE, SequenceRfDiscStopComplete, SequenceShutdownComplete, SequenceNfceeDiscComplete, nfccx/SequenceNfceeDiscComplete, SequencePreInit, nfccx/SequenceRfDiscStartComplete, nfccx/SequencePreRfDiscStop, nfccx/SequencePreRecovery, nfccx/SequencePreNfceeDisc, nfccx/SequenceRecoveryComplete, SequenceMaximum, nfccx/SequenceMaximum, nfccx/SequencePreShutdown, NFC_CX_SEQUENCE enumeration [Near-Field Proximity Drivers], nfccx/SequenceShutdownComplete
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : nfccx.h
req.include-header : Ncidef.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : None supported
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Requires same
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNFC_CX_SEQUENCE, NFC_CX_SEQUENCE"
---

# _NFC_CX_SEQUENCE Enumeration
The NFC_CX_SEQUENCE enumeration specifies sequences.

## Syntax
````
typedef enum _NFC_CX_SEQUENCE { 
  SequencePreInit              = 0,
  SequenceInitComplete         = 1,
  SequencePreRfDiscStart       = 2,
  SequenceRfDiscStartComplete  = 3,
  SequencePreRfDiscStop        = 4,
  SequenceRfDiscStopComplete   = 5,
  SequencePreNfceeDisc         = 6,
  SequenceNfceeDiscComplete    = 7,
  SequencePreShutdown          = 8,
  SequenceShutdownComplete     = 9,
  SequencePreRecovery          = 10,
  SequenceRecoveryComplete     = 11,
  SequenceMaximum              = 12
} NFC_CX_SEQUENCE;
````

## Constants

<table>

<tr>
<td>SequenceInitComplete</td>
<td>This sequence is invoked by CX during the idle to init state transition, that is, prior to start of initialization by NFC CX. No NCI commands including CORE_RESET_CMD has been sent to the NFC controller by NFC CX. In this sequence, the client can invoke any non-NCI command. NCI commands should not be sent to the controller since neither CORE_RESET_CMD nor CORE_INIT_CMD has been sent to the controller.</td>
</tr>

<tr>
<td>SequenceMaximum</td>
<td></td>
</tr>

<tr>
<td>SequenceNfceeDiscComplete</td>
<td>This sequence is invoked immediately post-NFCEE discovery operation.</td>
</tr>

<tr>
<td>SequencePreInit</td>
<td>This sequence is invoked by CX during the idle to init state transition, that is, prior to start of initialization by NFC CX. No NCI commands including CORE_RESET_CMD have been sent to the NFC controller by NFC CX. In this sequence, the client can invoke any non-NCI command. NCI commands should not be sent to the controller because neither CORE_RESET_CMD nor CORE_INIT_CMD has been sent to the controller.</td>
</tr>

<tr>
<td>SequencePreNfceeDisc</td>
<td>This sequence is invoked by CX prior to start of NFCEE discovery. The NFCEE discovery happens with the discovery loop deactivated. The client driver can use this sequence to enable any internal NFC-NFCEE interfaces which could have been disabled post-initialization for power optimizations.</td>
</tr>

<tr>
<td>SequencePreRecovery</td>
<td>This sequence is invoked by CX if it needs to perform a recovery sequence due to a fatal failure. The client driver can use this sequence to capture RAM dumps for diagnostic purposes.</td>
</tr>

<tr>
<td>SequencePreRfDiscStart</td>
<td>This sequence is invoked by CX prior to start of RF discovery i.e. through RF_DISCOVER_CMD. The client driver can use this opportunity to perform any related RF configuration including any optimizations to the discovery loop.</td>
</tr>

<tr>
<td>SequencePreRfDiscStop</td>
<td>This sequence is invoked by CX prior to stopping the RF discovery loop.</td>
</tr>

<tr>
<td>SequencePreShutdown</td>
<td>This sequence is invoked prior to start of shutdown.</td>
</tr>

<tr>
<td>SequenceRecoveryComplete</td>
<td>This sequence is invoked by the CX after the completion of the recovery sequence and when the driver is back to the work-state.</td>
</tr>

<tr>
<td>SequenceRfDiscStartComplete</td>
<td>This sequence is invoked by CX immediately after the start of RF discovery. Any configuration post-discovery start can be supported through this extensibility point.</td>
</tr>

<tr>
<td>SequenceRfDiscStopComplete</td>
<td>This sequence is invoked immediately after discovery loop is stopped. The client driver can use this extensibility point to enable any standby mode configuration.</td>
</tr>

<tr>
<td>SequenceShutdownComplete</td>
<td>This sequence is invoked by CX after shutdown sequence is complete. The client driver can clean up any NCI state maintained.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | nfccx.h (include Ncidef.h) |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_SEQUENCE enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>