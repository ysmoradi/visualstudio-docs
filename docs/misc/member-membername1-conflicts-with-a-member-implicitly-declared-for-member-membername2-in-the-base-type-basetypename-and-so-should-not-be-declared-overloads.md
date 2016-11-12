---
title: "Member &#39;&lt;membername1&gt;&#39; conflicts with a member implicitly declared for member &#39;&lt;membername2&gt;&#39; in the base type &#39;&lt;basetypename&gt;&#39; and so should not be declared &#39;Overloads&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40023"
  - "bc40023"
helpviewer_keywords: 
  - "BC40023"
ms.assetid: 82bb29a6-8d49-47a4-8c19-b21e97dfc7de
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Member &#39;&lt;membername1&gt;&#39; conflicts with a member implicitly declared for member &#39;&lt;membername2&gt;&#39; in the base type &#39;&lt;basetypename&gt;&#39; and so should not be declared &#39;Overloads&#39;
A property or procedure in a derived class uses the same name as an implicit member of the base class and specifies the [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) keyword.  
  
 Overloading is used to define multiple versions of a property or procedure all in the same class. You cannot define an additional version of a base class member unless that base class member already specifies `Overloads`. Because implicit members do not specify `Overloads`, the compiler assumes that this property or procedure [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) the implicit base class member.  
  
 The [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] compiler creates implicit members corresponding to certain programming elements you declare. The following table summarizes these implicit, or *synthetic*, members.  
  
|Declared element|Implicitly created members|  
|----------------------|--------------------------------|  
|Enumeration|`value__` member|  
|Event|`add_<eventname>` procedure<br /><br /> `remove_<eventname>` procedure<br /><br /> `<eventname>Event` field<br /><br /> `<eventname>EventHandler` delegate|  
|Property|`get_<propertyname>` procedure<br /><br /> `set_<propertyname>` procedure|  
|`My.Form` member, `My.WebService` member, or member of a class marked with the <xref:Microsoft.VisualBasic.MyGroupCollectionAttribute> attribute|`m_<variablename>` `Static` variable<br /><br /> `<variablename>` property<br /><br /> `get_<variablename>` procedure<br /><br /> `set_<variablename>` procedure|  
|`WithEvents` variable|`_<variablename>` variable<br /><br /> `<variablename>` property<br /><br /> `get_<variablename>` procedure<br /><br /> `set_<variablename>` procedure|  
  
 Because of the risk of name conflicts, you should avoid naming any declared programming element using the same form as any one of these implicit members. For example, you should avoid any element name that starts with `get_` or `set_`.  
  
 By default, this message is a warning. For more information about hiding warnings and treating warnings as errors, see [Configuring Warnings in Visual Basic](../ide/configuring-warnings-in-visual-basic.md).  
  
 **Error ID:** BC40023  
  
### To correct this error  
  
-   Change the name of the property or procedure to avoid conflicts with the names listed in the previous table.  
  
## See Also  
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)