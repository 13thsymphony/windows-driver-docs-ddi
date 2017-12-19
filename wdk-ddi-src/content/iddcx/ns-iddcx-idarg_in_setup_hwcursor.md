---
UID: NS.IDDCX.IDARG_IN_SETUP_HWCURSOR
title: IDARG_IN_SETUP_HWCURSOR
author: windows-driver-content
description: Gives information about new cursors associated with a monitor.
old-location: display\idarg_in_setup_hwcursor.htm
old-project: display
ms.assetid: 1e2c959c-0ebd-4464-ad47-96f432cb5c6b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDARG_IN_SETUP_HWCURSOR,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_IN_SETUP_HWCURSOR
req.alt-loc: iddcx.h
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
---

# IDARG_IN_SETUP_HWCURSOR structure



## -description

                 Gives information about new cursors associated with a monitor.



## -syntax

````
typedef struct IDARG_IN_SETUP_HWCURSOR {
  IDDCX_CURSOR_CAPS CursorInfo;
  HANDLE            hNewCursorDataAvailable;
} IDARG_IN_SETUP_HWCURSOR, *IDARG_IN_SETUP_HWCURSOR;
````


## -struct-fields

### -field CursorInfo


                     [in] Cursor information for this path.
                 


### -field hNewCursorDataAvailable


                     [in] An event handle that will be triggered when new cursor data is available.
                 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>