---
title: "템플릿 정책 및 속성 창 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 창에서 템플릿 정책"
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 템플릿 정책 및 속성 창
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트를 엔터프라이즈 템플릿 프로젝트 내에 포함 되어 있으면 해당 엔터프라이즈 템플릿 프로젝트에 정책을 적용할 수 있습니다.  템플릿 정책 제한 시스템 속성에 대 한 기본값을 설정, 속성 숨기기, 속성을 추가 하는 데 사용할 수 있습니다.  
  
 템플릿 정책을 사용 하 여 표시의 정보를 제어 하는  **속성** 창입니다 다른 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>솔루션 또는 프로젝트 수준에서 개체 속성을 제한 하려면 정책 템플릿을 사용할 수 있지만 구성 요소 수준에서 개체 속성을 처리 합니다.  즉  
  
-   메서드를 구현할 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> 에 표시 되는 내용을 결정 하는  **속성** 특정 개체에 대 한 창  
  
-   솔루션 및 프로젝트 수준에서는 템플릿 정책을 사용 하 여에 표시 되는 내용을 결정 하는  **속성** 창 이전에 지정 된 개체에 대 한  
  
 정책 서식 파일을 사용 하 여 특정 속성을 선택적으로 제한할 수 있는  **속성** 에서 창 때 지정 된 형식의 프로젝트 항목이 선택 되어  **솔루션 탐색기** 프로젝트의 개발 팀의 모든 구성원에 유용할 수 있습니다.  예를 들어, 정책 서식 파일을 사용 하 여 데이터베이스에 있는 모든 연결 문자열 정보를 개발자에 게 위로 설정 하 고 있습니다 연결 문자열을 읽기 전용으로 설정 합니다.  이렇게 하는 각 개발자가 보장 하는 방법은 데이터 액세스에 대 한 올바른 경로 사용을 제공할 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [속성 확장](../../extensibility/internals/extending-properties.md)