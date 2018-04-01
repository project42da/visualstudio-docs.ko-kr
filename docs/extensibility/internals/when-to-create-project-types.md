---
title: 프로젝트 유형을 만들어야 하는 경우 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project types, conditions for creating
ms.assetid: 26adc860-ee4a-4f5c-95e1-e41b207dd7e6
caps.latest.revision: 14
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f766619054ed1912d677ac08fad511cfd3a3dcb4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="when-to-create-project-types"></a>프로젝트 형식 만들어야 하는 경우
사용자 지정 하기 위한 기반을 제공 하는 새 프로젝트 형식을 만드는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자에 대 한 합니다. 그러나 만들 새 프로젝트 형식을 필요는 없습니다 모든 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자 지정 합니다. 새 프로젝트 형식을 시나리오에 필요한 지 여부를 결정 합니다. 다음 지침 도움이 됩니다.  
  
## <a name="create-a-new-project-type"></a>새 프로젝트 형식 만들기  
 사용자 지정 하려는 경우 프로젝트 형식을 만들어야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다음과 같은 방법 중 하나 이상을 수행 하도록 합니다.  
  
-   빌드에 참가할 배포, 구성 및 소스 제어 합니다.  
  
-   디버깅 지원을 제공 합니다.  
  
-   에 프로젝트 항목을 표시 **솔루션 탐색기**합니다.  
  
-   사용 하 여는 **프로젝트 열기** 또는 **새 프로젝트** 대화 상자.  
  
-   프로젝트 중첩을 지원 합니다.  
  
## <a name="extend-an-existing-project-type"></a>기존 프로젝트 형식 확장  
 새 프로젝트 형식을 사용할 수 있는 만들어야 할 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 수정 하거나 기존 프로젝트 형식의 동작을 확장 하려면 다음 방법으로 빌드 프로세스에 대 한 예를 들어 수정 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트:  
  
-   하나의 단위로 여러 파일을 사용 합니다.  
  
-   하위 항목의 계층으로 단일 파일을 표시 합니다.  
  
-   편집기 관련 명령을 컨텍스트를 표시 합니다.  
  
-   편집기에 대 한 서비스 컨텍스트를 표시 합니다.  
  
## <a name="use-an-existing-project-type"></a>기존 프로젝트 형식을 사용합니다  
 새 프로젝트를 만드는 경우에 따라 필요는 없습니다. 다음 표에서 작업에 대 한 프로젝트 유형을 만들 필요가 없습니다을 보여 줍니다.  
  
|작업|설명|  
|----------|-----------------|  
|명령 처리|모든 VSPackage 명령을 처리할 수 있습니다.|  
|편집기를 작성합니다.|사용자 지정 편집기를 등록할 수 있습니다. 자세한 내용은 참조 [문서 창과 편집기](http://msdn.microsoft.com/en-us/603625e1-62b6-413a-bc44-089346e166bc)합니다.|  
|Windows를 소유합니다.|새 프로젝트 형식을 추가 하지 않고 모두 도구 및 문서 창을 만들 수 있습니다.|  
|속성 창에서 속성을 노출|모든 개체 속성을 노출할 수 있습니다.|  
  
## <a name="create-a-project-subtype"></a>프로젝트 하위 형식 만들기  
 새 프로젝트 형식을 만들 필요 없이 관리 되는 프로젝트 형식을 확장 하 프로젝트 하위 형식에 사용할 수 있습니다. 프로젝트 하위 형식 COM 집계를 사용 하 여 Microsoft로 작성 된 관리 되는 프로젝트를 확장 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]합니다. COM 집계와 대부분의 관리 되는 프로젝트 시스템 구현을 다시 사용할 수 있으며 인터페이스를 지 원하는 사용 하 여 집계를 통해 특정 시나리오에 대 한 사용자 지정할 수 있습니다. 프로젝트 하위 형식에 대 한 자세한 내용은 참조 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 창과 편집기](http://msdn.microsoft.com/en-us/603625e1-62b6-413a-bc44-089346e166bc)   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Visual Studio의 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)