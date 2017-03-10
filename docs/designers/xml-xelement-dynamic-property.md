---
title: "Xml(XElement 동적 속성) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
caps.latest.revision: 2
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 9044821c2bfee0dba8ffa91f3d91afd565b8d957
ms.openlocfilehash: 3bd6e84a3e59033aeb5050c172439bccbd096082
ms.lasthandoff: 02/22/2017

---
# <a name="xml-xelement-dynamic-property"></a>Xml(XElement 동적 속성)
요소의 서식이 지정되지 않은 XML 내용을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
elem.Xml  
```  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 요소의 서식이 지정되지 않은 XML 내용을 나타내는 <xref:System.String>입니다.  
  
## <a name="remarks"></a>설명  
 이 속성은 `SaveOptions` 매개 변수가 <xref:System.Xml.Linq.SaveOptions>로 설정된 <xref:System.Xml.Linq.XNode?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> 메서드와 동급입니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAttribute 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)   
 [Value](../designers/value-xelement-dynamic-property.md)
