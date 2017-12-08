---
UID: NS.d3dkmthk._D3DKMT_VIDSCH_ESCAPE
title: D3DKMT_VIDSCH_ESCAPE
author: windows-driver-content
description: The D3DKMT_VIDSCH_ESCAPE structure describes how to control the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_vidsch_escape.htm
old-project: display
ms.assetid: 8e19e8a1-0cb6-4d57-862c-2e3a785b949b
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_VIDSCH_ESCAPE, D3DKMT_VIDSCH_ESCAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_VIDSCH_ESCAPE
req.alt-loc: d3dkmthk.h
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
req.iface: 
---

# D3DKMT_VIDSCH_ESCAPE structure



## -description
<p><b>Do not use the D3DKMT_VIDSCH_ESCAPE structure; it is for testing purposes only.</b></p>
<p>The D3DKMT_VIDSCH_ESCAPE structure describes how to control the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys) in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function.</p>


## -syntax

````
typedef struct _D3DKMT_VIDSCH_ESCAPE {
  D3DKMT_VIDSCHESCAPETYPE Type;
  union {
    BOOL   PreemptionControl;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
    BOOL   EnableContextDelay;
    struct {
      ULONG TdrControl;
      union {
        ULONG NodeOrdinal;
      };
    } TdrControl2;
#endif 
    BOOL   SuspendScheduler;
    ULONG  TdrControl;
    ULONG  SuspendTime;
  };
} D3DKMT_VIDSCH_ESCAPE;
````


## -struct-fields
<dl>

### -field Type

<dd>
<p>The escape type, of type <a href="..\d3dkmthk\ne-d3dkmthk--d3dkmt-vidschescapetype.md">D3DKMT_VIDSCHESCAPETYPE</a>, which is reserved and should not be used in your driver.</p>
</dd>

### -field PreemptionControl

<dd>
<p>Enable or disable preemption.</p>
</dd>

### -field EnableContextDelay

<dd>
<p>Enable or disable context delay.</p>
</dd>

### -field TdrControl2

<dd>
<dl>

### -field TdrControl

<dd>
<p>Control TDR.</p>
</dd>

### -field NodeOrdinal

<dd>
<p>Valid if <b>TdrControl</b> is set to a value of <b>D3DKMT_TDRDBGCTRLTYPE_ENGINETDR</b>.</p>
</dd>
</dl>
</dd>

### -field SuspendScheduler

<dd>
<p>Suspend or resume scheduler (obsolete).</p>
</dd>

### -field TdrControl

<dd>
<p>Control TDR.</p>
</dd>

### -field SuspendTime

<dd>
<p>Time period to suspend.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-escape.md">D3DKMT_ESCAPE</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a>
</dt>
<dt>
<a href="..\d3dkmthk\ne-d3dkmthk--d3dkmt-vidschescapetype.md">D3DKMT_VIDSCHESCAPETYPE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_VIDSCH_ESCAPE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
