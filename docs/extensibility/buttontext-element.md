---
title: "요소를 로드 합니다 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "로드 합니다 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소를 로드 합니다"
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# 요소를 로드 합니다
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 필드를 사용 하면 다양 한 메뉴에 나타나는 텍스트를 지정할 수 있습니다. 기본적으로는 `ButtonText` 요소 메뉴 컨트롤러에 나타납니다.`ButtonText` 다른 텍스트 필드가 비어 있으면도 요소 기본값이 됩니다.`ButtonText` 다른 텍스트 필드에 지정 된 경우에 요소를 비워 둘 수 없습니다.  
  
## 구문  
  
```  
<ButtonText>My Command</ButtonText>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[문자열 요소](../extensibility/strings-element.md)|텍스트 요소와 같은 그룹화 `ButtonText` 및 `CommandName`합니다.|  
  
## 텍스트 값  
 텍스트 값은 `ButtonText` 요소 메뉴 항목, 바로 가기 단축키 \+, 및 표시 되는 텍스트에 있는 다른 사용자 인터페이스 \(UI\) 요소에 대해 표시 되는 텍스트를 제공 합니다.  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)