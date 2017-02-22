---
title: "연결선의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 연결선"
ms.assetid: b1f24e8d-cdd7-4a5d-af37-1038f43b45c7
caps.latest.revision: 21
caps.handback.revision: 21
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 연결선의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

생성 된 디자이너의 도메인 관계를 연결선을 나타냅니다.  
  
 자세한 내용은 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)를 참조하십시오.  이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 커넥터 속성을 다음 표에 나열 된 있습니다.  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|색|색이이 커넥터입니다.|검정|  
|대시 스타일|회선 \(실선, 대시, 점, 일점 쇄선, 이점 쇄선, 또는 사용자 지정\)이이 커넥터에 대 한 대시 스타일입니다.|단색|  
|원본 끝 스타일|원본 끝 스타일이 커넥터 \(HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond, 또는 없음\)입니다.|없음|  
|대상 끝 스타일|대상 끝 스타일이 커넥터 \(HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond, 또는 없음\)입니다.|없음|  
|텍스트 색|이 커넥터와 연결 된 텍스트 decorators에 사용 되는 색입니다.|검정|  
|Thickness|이 커넥터에 대 한 선 두께에서 인치를 측정 합니다.|0.03125|  
|액세스 한정자|클래스의 액세스 수준 \(`public` 또는 `internal`\).|Public|  
|사용자 지정 특성|이 커넥터에서 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<none\>|  
|더블 생성 파생|경우 `True`, 기본 클래스 및 \(재정의 통해 사용자 지정을 지원 합니다\)는 partial 클래스를 모두 생성 됩니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|사용자 정의 생성자가|경우 `True`, 소스 코드의 사용자 지정 생성자를 제공 합니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|상속 한정자|상속 되는 커넥터에서 생성 되는 소스 코드의 종류에 설명 합니다 \(`none`, `abstract` 또는 `sealed`\).|없음|  
|기본 커넥터|이 커넥터의 기본 클래스입니다.|\(없음\)|  
|Name|이 커넥터의 이름입니다.|현재 이름|  
|Namespace|이 커넥터와 관련 된 네임 스페이스입니다.|현재 네임 스페이스|  
|도구 설명 형식|도구 설명 \(고정, 변수 또는 none\) 정의 하는 방법을 합니다.  고정 된 경우 다음 값은 `Fixed Tooltip Text` 속성입니다;이 도구 설명으로 사용 됩니다 다음 변수 경우 도구 설명에 사용자 지정 코드 정의 됩니다.|\<none\>|  
|참고|이 커넥터와 연결 된 비공식 메모 합니다.|\<none\>|  
|연결 경로 스타일|커넥터 라우팅에 사용 되는 스타일입니다.  A `Rectilinear` 커넥터 수 직각 턴 필요 합니다. `Straight` 커넥터를 하지 않습니다.|직각선|  
|속성으로 노출 된 색상<br /><br /> 속성으로 노출 된 대시 스타일<br /><br /> 속성으로 노출 된 두께<br /><br /> 텍스트 색을 노출합니다.|경우 `True`, 사용자 명시 된 셰이프의 속성을 설정할 수 있습니다.  이렇게 설정 하려면 도형 정의 마우스 오른쪽 단추로 클릭 하 고  **추가 노출**.|False|  
|설명|생성 된 디자이너를 문서화 하는 데 사용 합니다.|\<none\>|  
|표시 이름|이 커넥터에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|\<none\>|  
|고정 된 도구 설명 텍스트|고정 된 도구 설명에 사용 되는 텍스트입니다.|\<none\>|  
|도움말 키워드입니다.|이 요소에 대 한 F1 도움말 색인을 사용 하는 키워드입니다.|\<none\>|  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)