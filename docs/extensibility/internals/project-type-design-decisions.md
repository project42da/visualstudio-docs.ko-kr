---
title: "프로젝트 형식에 대 한 설계 결정 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 형식, 프로젝트 파일 지 속성"
  - "프로젝트 형식, 커밋 메커니즘"
  - "프로젝트 형식 항목"
  - "프로젝트 형식에 디자인 결정"
ms.assetid: f68671fe-fd7a-4e56-a0b5-330b0f1fedb1
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 프로젝트 형식에 대 한 설계 결정 사항
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

새 프로젝트 형식을 만들기 전에 프로젝트 형식에 대 한 몇 가지 디자인 결정을 내려야 합니다.  사용할 어떤 종류의 프로젝트에 포함할 항목, 프로젝트 파일 유지 하는 방법, 어떤 실천 모델을 결정 해야 합니다.  
  
## 프로젝트 항목  
 프로젝트 파일 또는 추상 개체를 사용 하 시겠습니까?  파일을 사용 하는 경우 참조 또는 디렉터리 기반 파일 입니까?  파일 또는 추상 개체 포함할 로컬 이나 원격 일 수 있습니까?  
  
 프로젝트에서 항목 파일을 수 있습니다 이거나 인터넷을 통해 보다 추상적인 개체 개체 데이터베이스 리포지토리 또는 데이터 연결에서와 같은 수 있습니다.  항목에 파일이 없으면 프로젝트 참조 기반 또는 디렉터리 기반 프로젝트 수 있습니다.  
  
 참조 기반 프로젝트에서 둘 이상의 프로젝트 항목이 나타날 수 있습니다.  그러나 항목을 나타내는 실제 파일이 한 디렉터리에 있습니다.  디렉터리 기반 프로젝트에서는 모든 프로젝트 항목이 디렉터리 구조에 존재합니다.  자세한 내용은 [NIB:Item Management in Projects](http://msdn.microsoft.com/ko-kr/762e606b-7f44-4b66-97a1-e30a703654a0)를 참조하십시오.  
  
 로컬 항목 같은 응용 프로그램이 설치 된 컴퓨터에 저장 됩니다.  별도 서버에 로컬 네트워크 또는 인터넷에서 다른 위치에서 원격 항목을 저장할 수 있습니다.  
  
## 프로젝트 파일 지 속성  
 데이터 구조적된 저장소 또는 일반적인 플랫 파일 시스템에 저장 됩니다?  프로젝트 고유 편집기 또는 표준 편집기를 사용 하 여 파일을 열 수 있습니다?  
  
 자신의 데이터를 유지 합니다 대부분의 응용 프로그램 데이터를 파일에 저장 하 고 다시 사용자가 검토 하거나 정보를 변경 해야 하는 경우 읽기.  
  
 구조적된 저장소, 복합 파일이 라고도 하는 구성 요소 개체 모델 \(COM\) 개체를 여러 개 유지 된 데이터 파일을 저장할 때 일반적으로 사용 됩니다.  구조적된 저장소에 단일 디스크 파일 몇 가지 서로 다른 소프트웨어 구성 요소를 공유할 수 있습니다.  
  
 프로젝트의 항목에 대 한 지 속성에 대 한 고려 하는 여러 옵션이 있습니다.  다음 옵션 중 하나를 수행할 수 있습니다.  
  
-   변경 된 경우 각 파일을 개별적으로 저장 합니다.  
  
-   많은 거래에서 하나의 캡처  **저장** 작업을 합니다.  
  
-   파일을 로컬에 저장 하는 서버에 게시 또는 프로젝트 항목을 저장 하는 데이터 연결 원격 개체에 있는 항목을 나타내는 경우 또 다른 방법을 사용 하 여.  
  
 지 속성에 대 한 자세한 내용은 참조 하십시오. [프로젝트 지 속성](../../extensibility/internals/project-persistence.md) 및 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md).  
  
## 프로젝트 약정 모델  
 유지 된 데이터 객체를 열 직접 모드 또는 트 랜 잭 트 모드?  
  
 데이터 개체를 직접 모드에서 열면 데이터에 대 한 변경 내용은 즉시 또는 사용자가 수동으로 파일을 저장 하는 경우 통합 됩니다.  
  
 트 랜 잭 트 모드를 사용 하 여 데이터 개체가 열려 있으면 변경 내용을 메모리에 임시 위치에 저장 됩니다 및 사용자가 수동으로 파일을 저장 하도록 선택 될 때까지 적용 됩니다.  그 당시 모든 변경 내용이 함께 발생 해야 하거나 변경할 수 없습니다.  
  
## 참고 항목  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [NIB:Item Management in Projects](http://msdn.microsoft.com/ko-kr/762e606b-7f44-4b66-97a1-e30a703654a0)   
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)   
 [프로젝트 지 속성](../../extensibility/internals/project-persistence.md)   
 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md)   
 [프로젝트 모델에 대 한 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md)   
 [프로젝트 형식 만들기](../../extensibility/internals/creating-project-types.md)