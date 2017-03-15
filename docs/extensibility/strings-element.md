---
title: "문자열 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "문자열 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, 문자열"
ms.assetid: 23a42074-a689-481d-824f-b43aa448f266
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 문자열 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

문자열 요소 있어야 최소한 **ButtonText** 자식 요소입니다. 다른 모든 자식 요소는 선택적입니다. 잘못 된 XML 등의 문자 '&' 및 ' \<' 엔터티로 코딩 해야 \('& amp;' 및 '& l t;' 등\).  
  
 텍스트 문자열에서 앰퍼샌드는 명령에 대 한 바로 가기 키를 지정합니다.  
  
## 구문  
  
```  
<Strings>  
  <ButtonText>... </ButtonText>  
  <CommandName>... </CommandName>  
</Strings>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|language|선택적 요소. Language \= "."입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|로드|이 필드와 명령 정의 다음 5 개의 텍스트 필드를 통해 다양 한 메뉴에 나타나는 텍스트를 지정할 수 있습니다. 기본적으로는 `ButtonText` 메뉴 컨트롤러에 필드가 나타납니다.`ButtonText` 다른 텍스트 필드가 비어 있으면 또한 필드의 기본값이 됩니다.`ButtonText` 다른 텍스트 필드에 지정 된 경우에 필드를 비워 둘 수 없습니다.|  
|ToolTipText|`ToolTipText` 필드 메뉴 항목에 대 한 도구 설명에 표시 되는 텍스트를 지정 합니다.<br /><br /> 하는 경우는 `ToolTipText` 필드가 비어는 `ButtonText` 필드가 사용 됩니다.|  
|MenuText|`MenuText` 주 메뉴에서 하위 메뉴 또는 바로 가기 메뉴에서 도구 모음에 명령에 대해 표시 되는 텍스트 필드를 지정 합니다. 하는 경우는 `MenuText` 필드가 비어, 통합된 개발 환경 \(IDE\)을 사용 하는 `ButtonText` 필드입니다.`MenuText` 필드 지역화를 위해 사용할 수도 있습니다.<br /><br /> 바로 가기 메뉴에 대해서는 `MenuText` 필드는 IDE에서 바로 가기 메뉴를 사용자 지정할 수 있는 바로 가기 메뉴 도구 모음에 표시 되는 이름입니다. 따라서 사용자 바로 가기 메뉴입니다; 이름에 특정 수 예를 들어 "바로 가기" 대신 "위젯 패키지 바로 가기 메뉴"를 사용 합니다.<br /><br /> 하는 경우는 `MenuText` 필드를 지정 하지 않으면는 `ButtonText` 필드가 사용 됩니다.|  
|CommandName|`CommandName` 키보드 범주에 표시 되는 텍스트를 지정 하는 필드는 **명령을** 탭에 **사용자 지정** 대화 상자 \(클릭 하 여 **사용자 지정** 에 **도구** 메뉴\).|  
|CanonicalName|영어 `CanonicalName` 필드에 입력할 수 있는 영어 텍스트에서 명령 이름을 지정는 **명령** 메뉴 항목을 실행 하는 창입니다. IDE 문자, 숫자, 밑줄, 마침표를 포함된 하지 않은 모든 문자가 제거 됩니다. 이 텍스트는 연결 하 여 다음의 `ButtonText` 명령을 정의 하는 필드입니다. 예를 들어 **새 프로젝트** 에 **파일** 메뉴 명령, File.NewProject 됩니다.<br /><br /> 경우 영어 `CanonicalName` 필드 지정 하지 않으면, IDE를 사용 하 여는 `ButtonText` 필드 및 문자, 숫자, 밑줄 및 마침표를 제외한 모든 줄무늬입니다. 예를 들어, 단추 텍스트 "& 정의 명령..."가 DefineCommands, 앰퍼샌드, 공간, 및 가변 매개 변수 제거 됩니다.<br /><br /> 경우는 `TextChanges` 플래그를 지정 하 고 해당 명령에서 인식 명령 텍스트가 변경 된 **명령** 창은 변경 되지 않습니다; 원래의 정규 형식이 그대로 유지 됩니다 `ButtonText` 또는 영어 `CanonicalName` 필드.|  
|LocCanonicalName|`LocCanonicalName` 필드는 영어를 동일 하 게 작동 하며 `CanonicalName` 필드는 하지만 지역화 된 명령 텍스트를 지정할 수 있습니다. 정식 두 필드를 지정할 수 있습니다. IDE는 방금에 입력 한 텍스트를 구문 분석 하기 때문에 **명령** 창과 연결 영어와 영어 이외의 텍스트 명령을 사용 하 여 동일한 명령에 연관 될 수 있습니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Button 요소](../extensibility/button-element.md)|사용자와 상호 작용할 수 있는 요소를 정의 합니다.|  
|[Menu 요소](../extensibility/menu-element.md)|단일 메뉴 항목을 정의합니다.|  
|[콤보 요소](../extensibility/combo-element.md)|콤보 상자에 표시 되는 명령을 정의 합니다.|  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)