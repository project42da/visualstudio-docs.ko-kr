---
title: "VSCT XML 스키마에 대 한 조건부 특성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSCT XML 스키마 요소, 조건부 특성"
  - "조건부 특성 (VSCT XML 스키마)"
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
caps.latest.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 5
---
# VSCT XML 스키마에 대 한 조건부 특성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모든 목록 및 항목에 조건부 특성을 적용할 수 있습니다. 논리 연산자와 기호 확장 식은 true 또는 false로 계산 합니다. True 이면 연결 된 목록이 나 항목이 결과 출력에 포함 됩니다.  
  
 다른 토큰 확장 또는 상수에 대 한 토큰 확장을 테스트할 수 있습니다. Defined\(\) 함수는 있는지 여부를 테스트는 특정 이름이 정의 된 값이 없는 경우에 사용 됩니다.  
  
 Condition 특성을 목록에 적용 되 면 조건 목록에서 모든 자식 요소에 적용 됩니다. 자체는 자식 요소 조건 특성이 있으면 다음 조건와 결합 됩니다 부모 식으로 AND 작업.  
  
 1 바이트, '1' 및 'true' 값을 true로 평가 하 고 0, '0' 및 'false' false로 평가 됩니다.  
  
## 연산자  
 조건부 식을 평가 하는 다음과 같은 연산자를 사용할 수 있습니다.  
  
|연산자|정의|  
|---------|--------|  
|\(,\)|그룹화|  
|\!|논리 NOT|  
|\<, \>, \<\=, \>\=, \=\=, \!\=|관계형 및 같음|  
|및|부울|  
|또는|부울|  
  
## 예제  
  
```  
<Menu Condition="Defined(DEBUG)" … </Menu> <Menu Condition="%(SKU_MODE) = 'Demo'" … </Menu> <Menus Condition="Defined(DEBUG)"> <Menu … </Menu> </Menus> <Menus Condition="Defined(DEMO_SKU)"> <Menus Condition="!Defined(DEBUG)"> <Menu … </Menu> </Menus> <Menu … </Menu> </Menus> <Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU)) and !Defined(DEBUG)"> <Menu … </Menu> </Menus>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)