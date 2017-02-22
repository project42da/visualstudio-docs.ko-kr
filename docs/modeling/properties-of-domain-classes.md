---
title: "도메인 클래스의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 도메인 클래스"
ms.assetid: a3993995-19e7-4761-a972-b1de89131a1b
caps.latest.revision: 21
caps.handback.revision: 21
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 도메인 클래스의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

도메인 클래스의 속성은 다음 표에 있습니다.  도메인 클래스에 대 한 자세한 내용은 [모델, 클래스 및 관계 이해](../modeling/understanding-models-classes-and-relationships.md).  이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|액세스 한정자|도메인 클래스의 액세스 수준 \(`public` 또는 `internal`\).|`public`|  
|사용자 지정 특성|이 도메인 클래스에서 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 됩니다.|\<none\>|  
|더블 생성 파생|경우 `True`, 기본 클래스 및 \(재정의 통해 사용자 지정을 지원 합니다\)는 partial 클래스를 모두 생성 됩니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|`False`|  
|사용자 정의 생성자가|경우 `True`, 소스 코드의 사용자 지정 생성자를 제공 합니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|`False`|  
|상속 한정자|상속 되는 도메인 클래스에서 생성 되는 소스 코드의 종류에 설명 합니다 \(`none`, `abstract` 또는 `sealed`\).|`none`|  
|기본 클래스|이 도메인 클래스를 파생 하는 경우 기본 클래스의 이름입니다.|\<none\>|  
|Name|이 도메인 클래스의 이름입니다.|현재 이름|  
|Namespace|이 도메인 클래스의 네임 스페이스입니다.|현재 네임 스페이스|  
|참고|이 도메인 클래스와 관련 된 비공식 메모 합니다.|\<none\>|  
|설명|생성 된 디자이너의 UI를 문서화 하는 데 사용 되는 설명입니다.|\<none\>|  
|표시 이름|이 도메인 클래스에 대해 생성 된 디자이너에 표시 되는 이름입니다.|\<none\>|  
|도움말 키워드입니다.|이 도메인 클래스에 대 한 F1 도움말 색인을 사용 하는 선택적 키워드입니다.|\<none\>|  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)