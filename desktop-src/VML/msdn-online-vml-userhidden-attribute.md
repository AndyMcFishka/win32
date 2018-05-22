---
title: VML UserHidden Attribute
description: VML UserHidden Attribute
ms.assetid: '0e4616c7-a456-4157-b77a-56cd289e913c'
---

# VML UserHidden Attribute

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Determines whether a script anchor is hidden. Read/write. **VgTriState**.

**Applies To**

[Shape](shape-element--vml.md)

**Tag Syntax**

&lt;v: *element* o:userhidden=" *expression* "&gt;

**Remarks**

The default is **False**. If **True**, script anchors stay hidden even if the shape is otherwise visible.

*Microsoft Office Extensions Attribute*

**Example**

The script anchor of the shape is hidden.


```HTML
   <v:rect id=myrect fillcolor="red" userhidden="True"
   style="position:relative;top:1;left:1;width:20;height:20">
   </v:rect>
```



 

 



