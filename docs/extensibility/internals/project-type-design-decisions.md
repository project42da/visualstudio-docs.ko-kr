---
title: 프로젝트 형식 디자인 관련 결정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project types, project file persistence
- project types, commitment mechanics
- project types, items
- project types, design decisions
ms.assetid: f68671fe-fd7a-4e56-a0b5-330b0f1fedb1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c28c6f29454feed94407d6e37c3432247b9a4a26
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="project-type-design-decisions"></a>프로젝트 형식에 대 한 디자인 관련 결정
새 프로젝트 형식을 만들기 전에 프로젝트 형식에 대 한 몇 가지 디자인 결정 해야 합니다. 사용할 항목을 프로젝트에 포함 됩니다, 프로젝트 파일은 지속 방법, 및 어떤 약정 모델의 유형을 결정 해야 합니다.  
  
## <a name="project-items"></a>프로젝트 항목  
 프로젝트를 파일이 나 추상 개체 사용 시겠습니까? 파일을 사용 하는 경우 이러한 됩니다 참조 또는 디렉터리 기반 파일? 로컬 또는 원격 파일 또는 진행 추상 개체?  
  
 프로젝트에서 항목에는 파일을 지정할 수 있습니다 하거나 인터넷을 통해 더 추상적인 개체 예: 데이터베이스 저장소 또는 데이터 연결의 개체 수 있습니다. 항목은 파일을 프로젝트 참조 기반 또는 디렉터리 기반 프로젝트 가능 합니다.  
  
 프로젝트 기반 참조에에서 항목이 둘 이상의 프로젝트에 나타날 수 있습니다. 그러나 항목 표시 하는 실제 파일은 디렉터리 하나에 있습니다. 디렉터리 기반 프로젝트에서 모든 프로젝트 항목의 디렉터리 구조에 존재 합니다.  
  
 로컬 항목은 응용 프로그램이 설치 되어 있는 동일한 컴퓨터에 저장 됩니다. 로컬 네트워크에 별도 서버 또는 다른 위치에서 인터넷에서 원격 항목을 저장할 수 있습니다.  
  
## <a name="project-file-persistence"></a>프로젝트 파일 지 속성  
 데이터에 일반적인 플랫 파일 시스템 또는 구조적된 저장소를 저장할 수 있습니까? 표준 편집기 또는 프로젝트 관련 편집기를 사용 하 여 파일 열립니다.  
  
 데이터를 유지 하기 위해 대부분의 응용 프로그램을 파일에 데이터를 저장 하 한 다음 사용자를 검토 하거나 정보를 변경 해야 하는 경우에 다시 읽습니다.  
  
 복합 파일 라고도 하는 구조적된 저장소는 여러 모델 COM (Component Object) 개체를 단일 파일로 지속형된 데이터를 저장 해야 경우에 일반적으로 사용 됩니다. 구조적된 저장소 여러 다른 소프트웨어 구성 요소는 단일 디스크 파일을 공유할 수 있습니다.  
  
 프로젝트의 항목에 대 한 지 속성에 대 한 고려해 야 할 몇 가지 옵션이 있습니다. 다음 옵션 중 하나를 수행할 수 있습니다.  
  
-   변경 된 경우 각 파일을 개별적으로 저장 합니다.  
  
-   단일에서 트랜잭션 캡처 **저장** 작업 합니다.  
  
-   파일을 로컬로 저장 하는 서버에 게시 하거나 항목이 원격 개체에 데이터 연결을 나타내는 경우 프로젝트 항목을 저장 하는 다른 접근 방식을 사용 합니다.  
  
 지 속성에 대 한 자세한 내용은 참조 [프로젝트 지 속성](../../extensibility/internals/project-persistence.md) 및 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)합니다.  
  
## <a name="project-commitment-model"></a>프로젝트 약정 모델  
 지속형된 데이터 개체를 열 수는 직접 모드 또는 트랜잭션된 모드에서?  
  
 데이터 개체는 직접 모드에서 열면 즉시 또는 사용자 파일을 수동으로 저장 하는 경우 데이터에 대 한 변경 내용이 통합 됩니다.  
  
 트랜잭션된 모드를 사용 하 여 데이터 개체를 열면 변경 내용이 메모리에 임시 위치에 저장 되 고 수동으로 파일을 저장 하도록 선택 될 때까지 커밋되지 않습니다. 해당 시간에 모든 변경 내용을 함께 발생 해야 하거나 변경 되지 것입니다 수 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)   
 [프로젝트 지 속성](../../extensibility/internals/project-persistence.md)   
 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md)   
 [프로젝트 모델에 대 한 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md)   
 [프로젝트 형식 만들기](../../extensibility/internals/creating-project-types.md)