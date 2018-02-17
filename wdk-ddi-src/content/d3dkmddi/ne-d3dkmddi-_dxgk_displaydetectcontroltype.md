---
UID: NE:d3dkmddi._DXGK_DISPLAYDETECTCONTROLTYPE
title: "_DXGK_DISPLAYDETECTCONTROLTYPE"
author: windows-driver-content
description: Enumeration indicating the type of display detection action.
old-location: display\dxgk_displaydetectcontroltype.htm
old-project: display
ms.assetid: D777342E-439E-4BEF-9DCC-7962B1AF8EAB
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_DISPLAYDETECTCONTROLTYPE, d3dkmddi/DXGK_DDCT_POLLALL, DXGK_DDCT_POLLONE, d3dkmddi/DXGK_DDCT_DISABLEHPD, display.dxgk_displaydetectcontroltype, DXGK_DDCT_UNINITIALIZED, DXGK_DISPLAYDETECTCONTROLTYPE enumeration [Display Devices], DXGK_DDCT_DISABLEHPD, d3dkmddi/DXGK_DDCT_UNINITIALIZED, d3dkmddi/DXGK_DISPLAYDETECTCONTROLTYPE, _DXGK_DISPLAYDETECTCONTROLTYPE, DXGK_DDCT_POLLALL, d3dkmddi/DXGK_DDCT_POLLONE, DXGK_DDCT_ENABLEHPD, d3dkmddi/DXGK_DDCT_ENABLEHPD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_DISPLAYDETECTCONTROLTYPE
product: Windows
targetos: Windows
req.typenames: DXGK_DISPLAYDETECTCONTROLTYPE
---

# _DXGK_DISPLAYDETECTCONTROLTYPE Enumeration
Enumeration indicating the type of display detection action.

## Syntax
````
typedef enum _DXGK_DISPLAYDETECTCONTROLTYPE { 
  DXGK_DDCT_UNINITIALIZED  = 0,
  DXGK_DDCT_POLLONE,
  DXGK_DDCT_POLLALL,
  DXGK_DDCT_ENABLEHPD,
  DXGK_DDCT_DISABLEHPD
} DXGK_DISPLAYDETECTCONTROLTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_DDCT_DISABLEHPD</td>
                    <td>Applies to all targets and requires that the driver disables new notifications. It is understood that, this does not prevent an in-flight notification from being reported after the driver has returned.</td>
                </tr>
            
                <tr>
                    <td>DXGK_DDCT_ENABLEHPD</td>
                    <td>Applies to all targets and requires that the driver enables new notifications and indicates any pending notifications using DxgkCbIndicateConnectorChange before completing the call.  It must also initiate polls for all targets where the driver does not have current status before completing the call but it should not wait for the results of polling before returning. For the POST adapter, it is important that the display which was initialized by firmware be included in the set of displays which is reported before returning from the call made during boot so that the OS is aware of the monitor before it requests the boot functional VidPn.  Since firmware has already detected and initialized the boot display and the driver has been able to query for the frame buffer state, the connection status should naturally be known by the driver and pending notification to the OS.</td>
                </tr>
            
                <tr>
                    <td>DXGK_DDCT_POLLALL</td>
                    <td>Request to initiate polls for all targets where the driver does not have current status before completing the call but the driver should not wait for the results of polling before returning.
As status of each target is discovered, if it is not the same as the previously updated status should be reported using DxgkCbIndicateConnectorChange.</td>
                </tr>
            
                <tr>
                    <td>DXGK_DDCT_POLLONE</td>
                    <td>Requests a poll of the target specified in the TargetId field.  The driver should initiate polling the target if the current status is not known.  If the status is not the same as the last reported status for the target, an updated status should be reported using DxgkCbIndicateConnectorChange.</td>
                </tr>
            
                <tr>
                    <td>DXGK_DDCT_UNINITIALIZED</td>
                    <td>Indicates that a variable of type DXGK_DISPLAYDETECTCONTROLTYPE has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>UINT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |