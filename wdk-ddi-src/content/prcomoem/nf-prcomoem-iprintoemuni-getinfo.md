---
UID: NF.prcomoem.IPrintOemUni.GetInfo
title: IPrintOemUni::GetInfo method
author: windows-driver-content
description: A rendering plug-in's IPrintOemUni::GetInfo method returns identification information.
old-location: print\iprintoemuni_getinfo.htm
old-project: print
ms.assetid: 8c4ab4a0-387f-49f8-bb9e-4851c5079cff
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemUni, IPrintOemUni::GetInfo, GetInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemUni.GetInfo
req.alt-loc: Prcomoem.h
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
req.product: Windows 10 or later.
---

# IPrintOemUni::GetInfo method



## -description
A rendering plug-in's <code>IPrintOemUni::GetInfo</code> method returns identification information.



## -syntax

````
STDMETHOD GetInfo(
   DWORD  dwMode,
   PVOID  pBuffer,
   DWORD  cbSize,
   PDWORD pcbNeeded
);
````


## -parameters

### -param dwMode 

Contains one of the following caller-supplied integer constants.




### -param OEMGI_GETREQUESTEDHELPERINTERFACES

The method must write the bit flag value of OEMPUBLISH_IPRINTCOREHELPER to the buffer <i>pBuffer</i> if the <a href="print.iprintoemuni_publishdriverinterface">IPrintOemUni::PublishDriverInterface</a> method should be called with parameter <i>pIUnknown</i> pointing to an object that implements the <a href="print.iprintcorehelperuni_interface">IPrintCoreHelperUni Interface</a>.

</dd>
</dl>



### -param OEMGI_GETSIGNATURE

The method must return a unique four-byte identification signature. The plug-in must also place this signature in <a href="print.optitem">OPTITEM</a> structures, as described in the description of the <a href="print.oemcuipparam">OEMCUIPPARAM</a>. structure's <b>pOEMOptItems</b> member.

</dd>
</dl>



### -param OEMGI_GETVERSION

The method must return the user interface plug-in's version number as a DWORD. The version format is developer-defined.

</dd>
</dl>

### -param pBuffer 

Caller-supplied pointer to memory allocated to receive the information specified by <i>dwInfo</i>.


### -param cbSize 

Caller-supplied size of the buffer pointed to by <i>pBuffer</i>.


### -param pcbNeeded 

Caller-supplied pointer to a location to receive the number of bytes written into the buffer pointed to by <i>pBuffer</i>.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.

 


## -remarks
A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::GetInfo</code> method, which is called immediately after the plug-in is loaded. The method should return the specified information by writing it to the address specified by <i>pBuffer</i> and writing the size, in bytes, of the returned information into the location specified by <i>pcbNeeded</i>.

If <i>pBuffer</i> is <b>NULL</b>, the method should just use <i>pcbNeeded</i> to return the number of bytes required to store the specified information.

For more information about creating and installing rendering plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintoemui_getinfo">IPrintOemUI::GetInfo</a>
</dt>
<dt>
<a href="print.iprintoemps_getinfo">IPrintOemPS::GetInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::GetInfo method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

