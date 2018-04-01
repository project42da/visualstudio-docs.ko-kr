---
title: 코드에 대 한 자동화를 제공 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e59f3826cbb2ed83510cd98209b4c83f9278397d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="providing-automation-for-code"></a>코드에 대 한 자동화를 제공합니다.
코드에 대 한 자동화 모델을 만들 필요는 없습니다. 환경 SDK 작업에 대 한 예제를 제공 하지 않습니다. 코드 모델에 대 한 정보를 참조 하십시오.는 <xref:EnvDTE.CodeModel> 개체입니다.  
  
 코드 모델을 구현 하려면 내부 데이터 구조에 의해 결정 된 모든 인터페이스를 구현 해야 합니다. 개체에서 파생 되어야 합니다는 `IDispatch` 클래스입니다.  
  
 확장할 수 있는 개체 <xref:EnvDTE.CodeModel> 및 <xref:EnvDTE.FileCodeModel>에서 사용할 수는 <xref:EnvDTE.Project> 개체를 다음과 같이 표시 합니다.  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 구현 하도록 선택할 수 있습니다만 `CodeModel` 또는 `FileCodeModel` 에서 반환할 개체의 인터페이스 프로그램 `Project` 및 <xref:EnvDTE.ProjectItem> 개체입니다. 프로젝트 시스템에 적합 한이 인터페이스에서 모든 기능을 제공 합니다.  
  
 메서드 또는 속성을 같은 기능을 추가 하려는 경우 사용할 수 없는 표준에서 `CodeModel` 및 `FileCodeModel` 인터페이스와 표준에서 상속 되는 인터페이스를 직접 만들 합니다. 최종 사용자가 쉽게 알 수 있도록 프로젝트 시스템과 상호 설명 해야 합니다. 표준 인터페이스를 반환 하지만 사용자는 호출할 수는 `QueryInterface` 메서드나 알려진 존재 하는 경우 사용자 인터페이스로 캐스팅 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [자동화 모델 개요](../../extensibility/internals/automation-model-overview.md)