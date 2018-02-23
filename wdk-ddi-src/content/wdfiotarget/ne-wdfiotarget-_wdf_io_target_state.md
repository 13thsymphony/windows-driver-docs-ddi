---
UID: NE:wdfiotarget._WDF_IO_TARGET_STATE
title: "_WDF_IO_TARGET_STATE"
author: windows-driver-content
description: The WDF_IO_TARGET_STATE enumeration specifies the states that an I/O target can be in.
old-location: wdf\wdf_io_target_state.htm
old-project: wdf
ms.assetid: 0189a83d-da46-49f1-99b8-8fb920009804
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdfiotarget/WdfIoTargetStopped, WDF_IO_TARGET_STATE, wudfddi_types/WdfIoTargetStopped, WDF_IO_TARGET_STATE enumeration, wdfiotarget/WdfIoTargetDeleted, wdfiotarget/WdfIoTargetClosed, WdfIoTargetDeleted, DFIOTargetRef_0dbd75b8-eb70-4996-8a13-80fb90f86dca.xml, wdfiotarget/PWDF_IO_TARGET_STATE, wdf.wdf_io_target_state, WdfIoTargetPurged, wudfddi_types/WdfIoTargetStateUndefined, WdfIoTargetStarted, wudfddi_types/WdfIoTargetClosedForQueryRemove, _WDF_IO_TARGET_STATE, WdfIoTargetClosed, wudfddi_types/WdfIoTargetDeleted, wudfddi_types/WdfIoTargetStarted, wudfddi_types/WdfIoTargetPurged, wudfddi_types/WDF_IO_TARGET_STATE, PWDF_IO_TARGET_STATE enumeration pointer, wdfiotarget/WDF_IO_TARGET_STATE, wdfiotarget/WdfIoTargetStateUndefined, wdfiotarget/WdfIoTargetClosedForQueryRemove, PWDF_IO_TARGET_STATE, WdfIoTargetClosedForQueryRemove, wdfiotarget/WdfIoTargetStarted, wudfddi_types/WdfIoTargetClosed, wdfiotarget/WdfIoTargetPurged, kmdf.wdf_io_target_state, *PWDF_IO_TARGET_STATE, wudfddi_types/PWDF_IO_TARGET_STATE, WdfIoTargetStopped, WdfIoTargetStateUndefined
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
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
-	wdfiotarget.h
-	wudfddi_types.h
apiname:
-	WDF_IO_TARGET_STATE
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# _WDF_IO_TARGET_STATE Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_STATE</b> enumeration specifies the states that an I/O target can be in.

## Syntax
````
typedef enum _WDF_IO_TARGET_STATE { 
  WdfIoTargetStateUndefined        = 0,
  WdfIoTargetStarted               = 1,
  WdfIoTargetStopped               = 2,
  WdfIoTargetClosedForQueryRemove  = 3,
  WdfIoTargetClosed                = 4,
  WdfIoTargetDeleted               = 5,
  WdfIoTargetPurged                = 6
} WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>WdfIoTargetClosed</td>
                    <td>The I/O target is permanently stopped and cannot process I/O requests.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetClosedForQueryRemove</td>
                    <td>The I/O target's underlying device might be removed in the near future.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetDeleted</td>
                    <td>The I/O target's underlying device has been removed.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetPurged</td>
                    <td>The I/O target is temporarily purged and cannot receive or process I/O requests. This constant is available starting in KMDF 1.11.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetStarted</td>
                    <td>The I/O target is started and can process I/O requests.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetStateUndefined</td>
                    <td>Reserved for internal use.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetStopped</td>
                    <td>The I/O target is temporarily stopped and cannot process I/O requests.</td>
                </tr>
</table>

## Remarks

To obtain an I/O target's current state, call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetgetstate.md">WdfIoTargetGetState</a>.

For more information about states for I/O targets, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 1.11 |
| **Header** | wdfiotarget.h (include Wdf.h) |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetgetstate.md">WdfIoTargetGetState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_STATE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>