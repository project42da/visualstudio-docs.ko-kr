---
title: "스윔 레인의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.dsltools.dsldesigner.swimlane"
helpviewer_keywords: 
  - "도메인별 언어, 스윔 레인"
ms.assetid: 47edbc2d-09e4-48ac-b4d1-5268a06a27e6
caps.latest.revision: 24
caps.handback.revision: 24
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 스윔 레인의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

스윔 레인은 다이어그램에 추가할 수 있습니다.  스윔 레인은 다이어그램 수직 또는 수평 영역으로 분할합니다.  다른 셰이프를 스윔 레인 안에 표시 되도록 정의할 수 있습니다.  자세한 내용은 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)를 참조하십시오.  이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 스윔 레인 속성을 다음 표에 나열 된 있습니다.  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|본문 채우기 색|스윔 레인은 본문의 채우기 색입니다.|흰색|  
|머리글 채우기 색|헤더에는 스윔 레인의 채우기 색입니다.|진한 회색|  
|구분 기호 색|구분선의 색입니다.|연한 회색|  
|구분 선 스타일|The style of the separator line \(`Solid`, `Dash`, `Dot`, `DashDot`, `DashDotDot`, or `Custom`\).|`Dash`|  
|구분 기호 두께|구분 선 인치에서 두께입니다.|0.03125|  
|텍스트 색|이 스윔 레인와 관련 된 텍스트 decorators에 사용 되는 색입니다.|검정|  
|액세스 한정자|클래스의 액세스 수준 \(`public` 또는 `internal`\).|Public|  
|사용자 지정 특성|이 스윔 레인에서 생성 되는 코드 클래스에 특성을 추가 하는 데 사용 됩니다.|\<none\>|  
|더블 생성 파생|경우 `True`, 기본 클래스 및 \(재정의 통해 사용자 지정을 지원 합니다\)는 partial 클래스를 모두 생성 됩니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|사용자 정의 생성자가|경우 `True`, 소스 코드의 사용자 지정 생성자를 제공 합니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|상속 한정자|상속 되는 스윔에서 생성 되는 소스 코드의 종류에 설명 합니다 \(`none`, `abstract` 또는 `sealed`\).|없음|  
|기본 스윔 레인|스윔이 레인이의 기본 클래스입니다.|\(없음\)|  
|Name|이 스윔 레인의 이름입니다.|현재 이름|  
|Namespace|이에 스윔이 레인 솔루션과 관련 된 네임 스페이스입니다.|현재 네임 스페이스|  
|도구 설명 형식|도구 설명 정의 된 방법 \(`fixed`, `variable`, 또는 `none`\).  경우 `fixed`, 다음 값은 `Fixed Tooltip Text` 입니다 속성을 사용 합니다. 경우 `variable`, 도구 설명 사용자 지정 코드를 정의 하 고 있습니다.|\<none\>|  
|참고|이 스윔 레인에 관련 된 비공식 메모 합니다.|\<none\>|  
|맞춤|가로 또는 세로 맞춤입니다.|세로|  
|처음 높이|초기 높이 인치에서이 스윔 레인입니다.  가로 스윔 레인에만 적용할 수 있습니다.|0|  
|초기 너비|이 인치에서 스윔이 레인의 초기 너비입니다.  세로 스윔 레인에만 적용할 수 있습니다.|0|  
|텍스트 색을 노출합니다.|경우 `True`, 사용자 생성 된 디자이너에는 스윔 레인의 색을 설정할 수 있습니다.  이 설정에 스윔 레인 셰이프를 마우스 오른쪽 단추로 클릭 하 고  **추가 노출**.|False|  
|설명|생성 된 디자이너를 문서화 하는 데 사용 합니다.|\<none\>|  
|표시 이름|이 스윔 레인 클래스를 참조 하는 생성 된 디자이너에 표시 되는 이름입니다.|\<none\>|  
|고정 된 도구 설명 텍스트|고정 된 도구 설명에 사용 되는 텍스트입니다.|\<none\>|  
|도움말 키워드입니다.|이 스윔 레인에 대 한 F1 도움말 색인을 사용 하는 키워드입니다.|\<none\>|  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)