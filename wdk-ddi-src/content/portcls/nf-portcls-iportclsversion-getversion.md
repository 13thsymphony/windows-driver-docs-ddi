---
UID: NF:portcls.IPortClsVersion.GetVersion
title: IPortClsVersion::GetVersion method
author: windows-driver-content
description: The GetVersion method returns the version of the Windows operating system that the driver is running on.
old-location: audio\iportclsversion_getversion.htm
old-project: audio
ms.assetid: ce1394e5-1d45-4b59-8738-fcb2cbe7cf51
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortClsVersion, IPortClsVersion::GetVersion, GetVersion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortClsVersion.GetVersion
req.alt-loc: portcls.h
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
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IPortClsVersion::GetVersion method



## -description
The <code>GetVersion</code> method returns the version of the Windows operating system that the driver is running on.



## -syntax

````
DWORD GetVersion(
    None
);
````


## -parameters

### -param None 


## -returns
The <code>GetVersion</code> method returns a DWORD value that specifies the Windows version number. For more information, see the following Remarks section.


## -remarks
The <code>GetVersion</code> method returns version information that specifies the Windows release.

The possible Windows version numbers that <code>GetVersion</code> can return are shown in the following table.

<b>kVersionWin98</b>

Windows 98


        no
       

<b>kVersionWin98SE</b>

Windows 98 Second Edition

<b>kVersionWin2K</b>

Windows 2000

<b>kVersionWin98SE_QFE2</b>

Windows 98 SE + Hot-Fix Package 269601 (See <a href="https://msdn.microsoft.com/8fcdc565-9d8a-45d9-9dc2-0420cbffc4f5">Additional Requirements for Windows 98</a>.)

<b>kVersionWin2K_SP2</b>

Windows 2000 + Service Pack 2

YES

<b>kVersionWinME</b>

Windows Me

<b>kVersionWin98SE_QFE3</b>

Reserved for future use

<b>kVersionWinME_QFE1</b>

<b>kVersionWinXP</b>

Windows XP

<b>kVersionWinXPSP1</b>

Windows XP + Service Pack 1

<b>kVersionWinServer2003</b>

Windows Server 2003

<b>kVersionWin2K_UAAQFE</b>

Windows 2000 + hot-fix package with IUnregister<i>Xxx</i> support (See <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.)

<b>kVersionWinXP_UAAQFE</b>

Windows XP + hot-fix package with IUnregister<i>Xxx</i> support (See <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.)

<b>kVersionWinServer2003_UAAQFE</b>

Windows Server 2003 + hot-fix package with IUnregister<i>Xxx</i> support (See <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.)

The version numbers in the preceding table are defined in header file portcls.h. Note that portcls.h defines version numbers both for Windows versions that do and do not support the <b>IPortClsVersion</b> interface. Both types of version number can be useful. A miniport driver typically contains a proprietary routine that determines the Windows version and can return any of the version numbers in the preceding table. When executed on a platform that does not support <b>IPortClsVersion</b>, this routine needs to use other software tests to determine the Windows version. These tests typically rely on the <a href="..\wdm\nf-wdm-ioiswdmversionavailable.md">IoIsWdmVersionAvailable</a> function. For a code example of such a routine, see the sb16 sample audio driver in the Windows Driver Kit (WDK).

The version numbers in the preceding table are listed in roughly chronological order. Each successive Windows version in the table does not necessarily represent a feature superset of the preceding version. For example, the version that is represented by <b>kVersionWin2K</b> has more audio features than the version that is represented by <b>kVersionWin98SE_QFE2</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iportclsversion.md">IPortClsVersion</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioiswdmversionavailable.md">IoIsWdmVersionAvailable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsVersion::GetVersion method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

