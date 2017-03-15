---
title: "방법: 요소에 CLR 특성 설정 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
ms.assetid: b3db3c74-920c-4701-9544-6f75cbe8b7c9
caps.latest.revision: 19
author: alancameronwills
ms.author: awills
manager: douge
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 7dcbd0005b80887dae91249a6781a6982414b9e5
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-set-clr-attributes-on-an-element"></a>방법: 요소에 CLR 특성 설정
사용자 지정 특성은 도메인 요소, 모양, 연결선, 및 다이어그램에 추가할 수 있는 특수 한 특성입니다. 상속 되는 모든 특성을 추가할 수는 `System.Attribute` 클래스입니다.  
  
### <a name="to-add-a-custom-attribute"></a>사용자 지정 특성을 추가 하려면  
  
1.  에 **DSL 탐색기**, 사용자 지정 특성을 추가 하려면 원하는 요소를 선택 합니다.  
  
2.  에 **속성** 창에서 다음을는 **사용자 지정 특성** 속성에서 찾아보기 (**... **) icon.  
  
     **속성 편집** 대화 상자가 열립니다.  
  
3.  에 **이름** 열을 클릭 ** \<특성을 추가 >** 특성의 이름을 입력 합니다. Enter 키를 누릅니다.  
  
4.  특성 이름에서 줄 괄호를 표시합니다. 이 줄에 입력 특성에 대 한 매개 변수 형식 (예를 들어 `string`), 한 다음 ENTER를 누릅니다.  
  
5.  에 **Name 속성** 열을 적절 한 이름을, 예를 들어 입력 `MyString`합니다.  
  
6.  **확인**을 클릭합니다.  
  
     **사용자 지정 특성** 이제 속성 형식에서 특성을 표시 합니다.  
  
     `[`*AttributeName* `(` *ParameterName* `=` *Type*`)]`  
  
## <a name="see-also"></a>참고 항목  
 [도메인별 언어 도구 용어집](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)
