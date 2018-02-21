---
UID: NE:ntifs._REFS_SMR_VOLUME_GC_ACTION
title: "_REFS_SMR_VOLUME_GC_ACTION"
author: windows-driver-content
description: The REFS_SMR_VOLUME_GC_ACTION enum contains the available garbage collection commands for FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS.
old-location: ifsk\refs_smr_volume_gc_action.htm
old-project: ifsk
ms.assetid: 9A9D174A-0E9E-4B3A-BF91-3000128C58C7
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: SmrGcActionStop, ntifs/REFS_SMR_VOLUME_GC_ACTION, SmrGcActionStart, ntifs/SmrGcActionStart, REFS_SMR_VOLUME_GC_ACTION, ntifs/SmrGcActionStartFullSpeed, _REFS_SMR_VOLUME_GC_ACTION, REFS_SMR_VOLUME_GC_ACTION enumeration [Installable File System Drivers], SmrGcActionStartFullSpeed, SmrGcActionPause, PREFS_SMR_VOLUME_GC_ACTION enumeration pointer [Installable File System Drivers], ntifs/SmrGcActionPause, ntifs/SmrGcActionStop, PREFS_SMR_VOLUME_GC_ACTION, *PREFS_SMR_VOLUME_GC_ACTION, ifsk.refs_smr_volume_gc_action, ntifs/PREFS_SMR_VOLUME_GC_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
-	Ntifs.h
apiname:
-	REFS_SMR_VOLUME_GC_ACTION
product: Windows
targetos: Windows
req.typenames: REFS_SMR_VOLUME_GC_ACTION, *PREFS_SMR_VOLUME_GC_ACTION
---

# _REFS_SMR_VOLUME_GC_ACTION Enumeration
The <b>REFS_SMR_VOLUME_GC_ACTION</b> enum contains the available garbage collection commands for <a href="https://msdn.microsoft.com/782542C4-CFC5-4BF7-AF38-3247A3AC6AB9">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>.

## Syntax
````
typedef enum _REFS_SMR_VOLUME_GC_ACTION { 
  SmrGcActionStart           = 1,
  SmrGcActionStartFullSpeed  = 2,
  SmrGcActionPause           = 3,
  SmrGcActionStop            = 4
} REFS_SMR_VOLUME_GC_ACTION, *PREFS_SMR_VOLUME_GC_ACTION;
````

## Constants

<table>
            
                <tr>
                    <td>SmrGcActionPause</td>
                    <td>Specifies to temporarily stop the garbage collection if it's in progress.  If the garbage collection is not in progress, there will be no operation.</td>
                </tr>
            
                <tr>
                    <td>SmrGcActionStart</td>
                    <td>Specifies to start garbage collection or resume from a previously paused garbage collection.  By default, garbage collection is off on Shingled Magnetic Recording (SMR) volumes.  Only users with admin rights can modify this setting.</td>
                </tr>
            
                <tr>
                    <td>SmrGcActionStartFullSpeed</td>
                    <td>Specifies to start or resume garbage collection at full speed.  Issuing Read/ Write I/O up to one SMR band size (256mb) at a time.</td>
                </tr>
            
                <tr>
                    <td>SmrGcActionStop</td>
                    <td>Specifies to stop the garbage collection process and removes the ability to resume.  If garbage collection was paused previously, this will clear the ability to resume from the point of the pause.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10, version 1709. Available starting with Windows 10, version 1709. |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/782542C4-CFC5-4BF7-AF38-3247A3AC6AB9">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20REFS_SMR_VOLUME_GC_ACTION enumeration%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>