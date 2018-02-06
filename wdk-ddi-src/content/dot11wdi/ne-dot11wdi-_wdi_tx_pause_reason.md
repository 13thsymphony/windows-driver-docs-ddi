---
UID: NE:dot11wdi._WDI_TX_PAUSE_REASON
title: "_WDI_TX_PAUSE_REASON"
author: windows-driver-content
description: The WDI_TX_PAUSE_REASON enumeration defines the reasons for a TX pause.
old-location: netvista\wdi_tx_pause_reason.htm
old-project: netvista
ms.assetid: 2585d243-e3b0-414d-a932-28d91b69f1f4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_TX_PAUSE_REASON_IHV_START, WDI_TX_PAUSE_REASON enumeration [Network Drivers Starting with Windows Vista], _WDI_TX_PAUSE_REASON, dot11wdi/WDI_TX_PAUSE_REASON_PS, netvista.wdi_tx_pause_reason, dot11wdi/WDI_TX_PAUSE_REASON_IHV_START, WDI_TX_PAUSE_REASON, WDI_TX_PAUSE_REASON_CREDIT, dot11wdi/WDI_TX_PAUSE_REASON_PEER_CREATE, WDI_TX_PAUSE_REASON_PS, dot11wdi/WDI_TX_PAUSE_REASON, dot11wdi/WDI_TX_PAUSE_REASON_IHV_END, WDI_TX_PAUSE_REASON_NULL, dot11wdi/WDI_TX_PAUSE_REASON_NULL, WDI_TX_PAUSE_REASON_IHV_END, netvista.wifi_tx_pause_reason, dot11wdi/WDI_TX_PAUSE_REASON_CREDIT, WDI_TX_PAUSE_REASON_PEER_CREATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	WDI_TX_PAUSE_REASON
product: Windows
targetos: Windows
req.typenames: WDI_TX_PAUSE_REASON
---

# _WDI_TX_PAUSE_REASON Enumeration
The WDI_TX_PAUSE_REASON enumeration defines the reasons for a TX pause.

## Syntax
````
typedef enum _WDI_TX_PAUSE_REASON { 
  WDI_TX_PAUSE_REASON_NULL         = 0x00000000,
  WDI_TX_PAUSE_REASON_CREDIT       = 0x00000001,
  WDI_TX_PAUSE_REASON_PEER_CREATE  = 0x00000002,
  WDI_TX_PAUSE_REASON_PS           = 0x00000004,
  WDI_TX_PAUSE_REASON_IHV_START    = 0x01000000,
  WDI_TX_PAUSE_REASON_IHV_END      = 0x80000000
} WDI_TX_PAUSE_REASON;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_TX_PAUSE_REASON_CREDIT</td>
                    <td>General reason to use for the exhaustion of some IHV resource.</td>
                </tr>
            
                <tr>
                    <td>WDI_TX_PAUSE_REASON_IHV_END</td>
                    <td>Inclusive end of range of valid pause reasons for IHV use.</td>
                </tr>
            
                <tr>
                    <td>WDI_TX_PAUSE_REASON_IHV_START</td>
                    <td>Inclusive beginning of range of valid pause reasons for IHV use.</td>
                </tr>
            
                <tr>
                    <td>WDI_TX_PAUSE_REASON_NULL</td>
                    <td>Reserved.  This enum value does not represent a valid pause reason code.</td>
                </tr>
            
                <tr>
                    <td>WDI_TX_PAUSE_REASON_PEER_CREATE</td>
                    <td>All TIDs on a newly created peer are paused with this reason.  The IHV uses this reason code to restart these TIDs.  This is only applicable when the <b>TargetPriorityQueueing</b> capability is set to false.</td>
                </tr>
            
                <tr>
                    <td>WDI_TX_PAUSE_REASON_PS</td>
                    <td>The peer is in Power Save Mode. This is only applicable when the <b>TargetPriorityQueueing</b> capability is set to false.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |

    ## See Also

        <a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDI_TX_PAUSE_REASON enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>