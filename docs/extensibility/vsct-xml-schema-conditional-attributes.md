---
title: VSCT XML 스키마에 대 한 조건부 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 975ca2f5fa6f070baf07b26cbfa0d8c3aa3b67d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="vsct-xml-schema-conditional-attributes"></a>VSCT XML 스키마에 대 한 조건부 특성
모든 목록 및 항목에 조건부 특성을 적용할 수 있습니다. 논리 연산자와 기호 확장 식은 true 또는 false로 계산 합니다. True 이면 연결 된 목록 또는 항목 결과 출력에 포함 됩니다.  
  
 다른 토큰 확장 또는 상수에 대 한 토큰 확장을 테스트할 수 있습니다. 함수 Defined() 있는지 여부를 테스트는 특정 이름이 정의 되어 값이 없는 경우에 사용 됩니다.  
  
 Condition 특성을 목록에 적용 되 면 조건이 목록에 모든 자식 요소에 적용 됩니다. 자체는 자식 요소 조건 특성이 포함 되어 다음 조건이 결합 되어 부모 식과 AND 연산에 의해 합니다.  
  
 1 바이트, '1' 및 'true' 값을 true로 평가 하 고 0, '0' 및 'f'는 false로 평가 됩니다.  
  
## <a name="operators"></a>연산자  
 조건부 식을 평가 하는 다음과 같은 연산자를 사용할 수 있습니다.  
  
|연산자|정의|  
|--------------|----------------|  
|(,)|그룹화|  
|!|논리 NOT|  
|\<, >, \<=, >=, ==, !=|관계형 및 같음|  
|를 갖는|부울|  
|또는|부울|  
  
## <a name="examples"></a>예제  
  
```  
<Menu Condition="Defined(DEBUG)" ...  
</Menu>  
  
<Menu Condition="%(SKU_MODE) = 'Demo'" ...  
</Menu>  
  
<Menus Condition="Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="Defined(DEMO_SKU)">  
    <Menus Condition="!Defined(DEBUG)">  
        <Menu ...  
        </Menu>  
    </Menus>  
  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU))   
and !Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)