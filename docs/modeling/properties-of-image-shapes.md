---
title: "이미지 모양의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.dsltools.dsldesigner.selectimagedialog"
  - "vs.dsltools.dsldesigner.imageshape"
helpviewer_keywords: 
  - "도메인별 언어, 이미지 모양"
ms.assetid: 9ce00ccd-07f2-4640-ac96-2a60481d0d72
caps.latest.revision: 25
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 25
---
# 이미지 모양의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이미지 셰이프를 사용 도메인 클래스에서 생성 된 디자이너를 표시 하는 방법을 지정할 수 있습니다.  설정 하 여 이미지 모양을 정의 `Image` 클래스에 미리 정의 된 이미지 파일의 속성입니다.  다음 형식이 지원 됩니다.  
  
-   .gif  
  
-   .jpg  
  
-   .jpeg  
  
-   .bmp  
  
-   .wmf  
  
-   .emf  
  
-   png  
  
 이미지 파일 등 디자이너 리소스 파일에는 기본적으로는  **리소스**폴더에 있는  **Dsl** 프로젝트입니다.  
  
 자세한 내용은 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)를 참조하십시오.  이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 이미지 셰이프 속성을 다음 표에 나열 된 있습니다.  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|채우기 색|이 셰이프의 채우기 색입니다.|흰색|  
|채우기 그라데이션 모드|이 셰이프의 채우기 그라데이션 모드입니다.|Horizontal|  
|기본 연결 지점을 했습니다.|경우 `True`셰이프 위쪽, 아래쪽, 왼쪽, 사용 하 고 올바른 연결점에 생성 된 디자이너입니다.|False|  
|외곽선 색상|이 셰이프의 윤곽선 색입니다.|검정|  
|대시 스타일 개요|개요 대시 스타일 \(솔리드, 대시, 점, 일점 쇄선, 이점 쇄선, 또는 사용자 지정\)이이 셰이프입니다.|단색|  
|윤곽선 두께|이 도형의 윤곽선 두께입니다.|0.03125|  
|텍스트 색|이 셰이프와 연관 된 텍스트 decorators에 사용 되는 색입니다.|검정|  
|액세스 한정자|셰이프 기 하 도형 \(공용 또는 내부\) 액세스 한정자입니다.|Public|  
|사용자 지정 특성|이 도형에서 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<none\>|  
|더블 생성 파생|경우 `True`, 기본 클래스 및 \(재정의 통해 사용자 지정을 지원 합니다\)는 partial 클래스를 모두 생성 됩니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|사용자 정의 생성자가|경우 `True`, 소스 코드의 사용자 지정 생성자를 제공 합니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.|False|  
|상속 한정자|상속 되는 이미지가 도형에서 생성 되는 소스 코드의 종류에 설명 합니다 \(`none`, `abstract` 또는 `sealed`\).|없음|  
|기본 이미지 셰이프|이 셰이프는 기본 클래스입니다.|\(없음\)|  
|Name|이 셰이프의 이름입니다.|현재 이름|  
|Namespace|이 셰이프와 관련 된 네임 스페이스입니다.|현재 네임 스페이스|  
|도구 설명 형식|\(고정, 변수 또는 없음\) 도구 설명이 정의 되어 있는 곳입니다.  고정 된 경우 다음 값은 `Fixed Tooltip Text` 속성입니다;이 도구 설명으로 사용 됩니다 다음 변수 경우 도구 설명에 사용자 지정 코드 정의 됩니다.|없음|  
|참고|이 도형에 연결 되어 비공식 메모 합니다.|\<none\>|  
|처음 높이|초기 높이 인치에서이 셰이프입니다.|1|  
|초기 너비|이 셰이프의 인치에서 초기 너비입니다.|1.5|  
|속성으로 노출 된 채우기 색<br /><br /> 노출 된 그라데이션 채우기 모드<br /><br /> 윤곽선 색 속성으로 노출<br /><br /> 개요 대시 스타일 속성으로 노출<br /><br /> 윤곽선 두께 속성으로 노출합니다.<br /><br /> 텍스트 색을 노출합니다.|경우 `True`, 사용자 명시 된 셰이프의 속성을 설정할 수 있습니다.  이렇게 설정 하려면 도형 정의 마우스 오른쪽 단추로 클릭 하 고  **추가 노출**.|False|  
|설명|생성 된 디자이너를 문서화 하는 데 사용 합니다.|\<none\>|  
|표시 이름|이 도형에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|\<none\>|  
|고정 된 도구 설명 텍스트|고정 된 도구 설명에 사용 되는 텍스트입니다.|\<none\>|  
|도움말 키워드입니다.|이 요소에 대 한 F1 도움말 색인을 사용 하는 키워드입니다.|\<none\>|  
|Image|이 도형에 사용 되는 이미지 파일의 경로입니다.|\<none\>|  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)