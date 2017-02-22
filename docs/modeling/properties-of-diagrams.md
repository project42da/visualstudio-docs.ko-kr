---
title: "다이어그램의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.dsltools.dsldesigner.dsldiagram"
helpviewer_keywords: 
  - "도메인별 언어, 다이어그램"
ms.assetid: 00bba4b8-6aa6-4027-96cb-4f4c41a77d3c
caps.latest.revision: 25
caps.handback.revision: 25
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 다이어그램의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

디자이너에서 생성 된 다이어그램 모양을 지정 하는 속성을 설정할 수 있습니다.  예를 들어 다이어그램에서 텍스트의 기본 색을 지정할 수 있습니다.  
  
 자세한 내용은 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)를 참조하십시오.  이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 다음 표에 다이어그램의 속성을 나열합니다.  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|채우기 색|다이어그램의 채우기 색입니다.|흰색|  
|텍스트 색|다이어그램에 표시 되는 텍스트의 색입니다.|검정|  
|액세스 한정자|\(공용 또는 내부\) 클래스의 액세스 한정자입니다.|Public|  
|사용자 지정 특성|생성 되는 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<none\>|  
|더블 생성 파생|경우 `True`, 기본 클래스 및 \(재정의 통해 사용자 지정을 지원 합니다\)는 partial 클래스를 모두 생성 됩니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|사용자 정의 생성자가|경우 `True`, 소스 코드의 사용자 지정 생성자를 제공 합니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|상속 한정자|상속 되는 다이어그램에서 생성 되는 소스 코드의 종류에 설명 합니다 \(`none`, `abstract` 또는 `sealed`\).|없음|  
|기본 다이어그램|이 다이어그램의 기본 클래스입니다.|\(없음\)|  
|Name|이 다이어그램의 이름입니다.|현재 이름|  
|Namespace|이 다이어그램에 관련 된 네임 스페이스입니다.|현재 네임 스페이스|  
|클래스를 표시|이 다이어그램을 나타내는 루트 도메인 클래스입니다.|해당 되는 경우 현재 루트 클래스|  
|참고|이 요소와 관련 된 비공식 메모 합니다.|\<none\>|  
|속성으로 노출 채우기 색|경우 `True`, 사용자 생성 된 디자이너 다이어그램의 채우기 색을 설정할 수 있습니다.  이렇게 설정 하려면 다이어그램 셰이프를 마우스 오른쪽 단추로 클릭 하 고  **추가 Explosed**.|False|  
|텍스트 색을 속성으로 노출합니다.|경우 `True`, 사용자 생성 된 디자이너에는 다이어그램의 텍스트 색을 설정할 수 있습니다.  이렇게 설정 하려면 다이어그램 셰이프를 마우스 오른쪽 단추로 클릭 하 고  **추가 Explosed**.|False|  
|설명|생성 된 디자이너를 문서화 하는 데 사용 되는 설명입니다.|\<none\>|  
|표시 이름|이 다이어그램에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|\<none\>|  
|도움말 키워드입니다.|이 다이어그램에 대 한 F1 도움말 색인을 사용 하는 키워드입니다.|\<none\>|  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)