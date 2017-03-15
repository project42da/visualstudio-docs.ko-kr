---
title: "CreateExpInstance 유틸리티 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "실험적 빌드"
  - "실험 하이브"
  - "실험적 인스턴스"
  - "createexpinstance"
  - "createexpinst"
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# CreateExpInstance 유틸리티
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

를 다시 만들려는 CreateExpInstance 유틸리티를 사용 하거나 Visual Studio의 실험적 인스턴스를 삭제 합니다. 디버깅 하 고 내부 제품을 변경 하지 않고 Visual Studio 확장을 테스트 실험적 인스턴스를 사용할 수 있습니다.  
  
## 구문  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### 매개 변수  
 \/ 만들기  
 실험적 인스턴스를 만듭니다.  
  
 \/ 다시 설정  
 실험적 인스턴스를 삭제 하 고 새를 만듭니다.  
  
 \/Clean  
 실험적 인스턴스를 삭제합니다.  
  
 \/ VSInstance  
 복사할 기본 Visual Studio 인스턴스를 포함 하는 디렉터리의 이름입니다.  
  
 \/ RootSuffix  
 실험적 인스턴스 디렉터리의 이름에 추가할 접미사입니다.  
  
## 설명  
 Visual Studio 확장에서 작업 하는 현재 확장을 설치 하 고 기본 실험적 인스턴스를 열고 f5 키를 눌러 수 있습니다. 실험적 인스턴스를 사용할 수 있는 경우 Visual Studio 기본 설정이 있는 하나 만듭니다.  
  
 실험적 인스턴스에서의 기본 위치는 Visual Studio 버전 번호에 따라 달라 집니다. 예를 들어 Visual Studio 2015의 위치는 %localappdata%\\Microsoft\\VisualStudio\\14.0Exp\\ 디렉터리 위치에 있는 모든 파일에는 해당 인스턴스의 일부로 간주 됩니다. 기본 위치에 디렉터리 이름이 변경 되지 않는 한 Visual Studio에서 추가 실험적 인스턴스를 로드 되지 않습니다.  
  
 Visual Studio 실험적 인스턴스를 열 때 시스템 레지스트리를 액세스 하지 않습니다. 이 레지스트리 하이브의 실험적 버전을 사용 하는 Visual Studio의 이전 버전에서 다릅니다.  
  
 CreateExpInstance 유틸리티 VsRegEx 유틸리티를 대체합니다.  
  
 다음 예제에서는 Visual Studio의 기본 실험적 인스턴스 다시 설정합니다.  
  
 **CreateExpInstance.exe \/Reset \/VSInstance 14.0 \= \/RootSuffix Exp \=**  
  
## 참고 항목  
 [제품 릴리스](../../misc/releasing-a-visual-studio-integration-product.md)