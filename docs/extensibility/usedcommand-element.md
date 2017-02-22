---
title: "UsedCommand 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UsedCommands 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, UsedCommands"
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# UsedCommand 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPackage에 다른.vsct 파일에 정의 된 명령에 액세스할 수 있습니다. 예를 들어 표준을 사용 하 여 VSPackage **복사** 명령으로 정의 되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셸 명령을 추가할 수 있습니다는 메뉴 또는 도구 모음을 다시 구현 하지 않고 있습니다.  
  
## 구문  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. 명령을 식별 하는 GUID ID 쌍의 GUID입니다.|  
|ID|필수 요소. 명령을 식별 하는 GUID ID 쌍의 ID입니다.|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|없음||  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[UsedCommands 요소](../extensibility/usedcommands-element.md)|UsedCommand 요소 그룹 및 기타 UsedCommands 그룹화 합니다.|  
  
## 설명  
 명령을 추가 하 여는 `<UsedCommands>` 요소를 VSPackage 알립니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경 VSPackage 명령에 필요 합니다. 추가 해야는 `<UsedCommand>` 요소 패키지에 필요한 모든 명령에 대 한 모든 버전 및 Visual Studio의 구성에 포함 될 수 있습니다. 예를 들어, Visual c \+ \+에만 적용 되는 명령을 호출 하는 패키지, 명령 됩니다 Visual Web Developer의 사용자에 게 사용할 수 있는 포함 하지 않으면는 `<UsedCommand>` 명령에 대 한 요소입니다.  
  
## 예제  
  
```  
<UsedCommands> <UsedCommand guid="guidVSStd97" id="cmdidCut"/> <UsedCommand guid="guidVSStd97" id="cmdidCopy"/> <UsedCommand guid="guidVSStd97" id="cmdidPaste"/> </UsedCommands>  
```  
  
## 참고 항목  
 [UsedCommands 요소](../extensibility/usedcommands-element.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)