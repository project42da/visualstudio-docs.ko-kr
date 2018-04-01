---
title: 소스 제어 디자인 결정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], design decisions
ms.assetid: 5f60ec1a-5a74-4362-8293-817a4dd73872
caps.latest.revision: 12
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4c1a512e104a092ae98ac86dc5e731fd1732aa33
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-design-decisions"></a>소스 제어에 대 한 디자인 관련 결정
다음과 같은 디자인 관련 결정 소스 제어를 구현 하는 경우 프로젝트에 대해 고려할 수 있습니다.  
  
## <a name="will-information-be-shared-or-private"></a>공유 또는 전용 정보 수는?  
 만들 수 있습니다는 가장 중요 한 디자인 결정에는 정보를 공유할 수 이며 개인입니다. 예를 들어 프로젝트에 대 한 파일 목록 전체에서 공유 하지만이 파일 목록 내에서 일부 사용자 개인 파일을 하려는. 컴파일러 설정을 공유 하지만 시작 프로젝트는 일반적으로 전용입니다. 설정은 순수 하 게 공유, 재정의 하면 공유 하거나 비공개로 순수 하 게 됩니다. 기본적으로 개인 항목 솔루션 사용자 옵션 (.suo) 파일을 같은 하지에 체크 인 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]합니다. .Suo 파일 또는 예를 들어 만들 특정 개인 파일을 같은 개인 파일의 모든 개인 정보를 저장 해야는. csproj.user 파일에 대 한 Visual C# 또는. vbproj.user 파일 Visual basic의 경우.  
  
 이 결정은 고-항목으로 만들 수 있습니다.  
  
## <a name="will-the-project-include-special-files"></a>프로젝트 특별 한 파일이 포함 됩니다.  
 또 다른 중요 한 디자인 결정에 프로젝트 구조 특수 한 파일을 사용 하는지 여부입니다. 특수 한 파일은 솔루션 탐색기에서 마우스 체크 인에 표시 되 고 체크 아웃 대화 상자에 있는 파일의 기반이 되는 숨겨진된 파일입니다. 특수 한 파일을 사용 하는 경우 다음이 지침을 따르십시오.  
  
1.  프로젝트 루트 노드를 사용 하는 특수 한 파일을 연결 하지 마십시오-즉, 프로젝트 파일 자체입니다. 프로젝트 파일에는 단일 파일 이어야 합니다.  
  
2.  특수 한 파일 추가, 제거 또는 적절 한 프로젝트에서 이름을 바꾼 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> 파일은 특수 한 파일을 나타내는 플래그가 설정 된 이벤트를 발생 해야 합니다. 이러한 이벤트는 적절 한 호출 프로젝트에 대 한 응답으로 환경에서 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 메서드.  
  
3.  프로젝트 또는 편집기 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 파일의 경우 해당 파일에 연결 된 특수 한 파일 자동으로 체크 아웃 되지 않은 합니다. 부모 파일과 함께 특수 한 파일을 전달 합니다. 환경에서는에 전달 되는 모든 파일 간의 관계를 검색 하 고 적절 하 게 체크 아웃 UI에 특수 한 파일을 숨깁니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [소스 제어 지원](../../extensibility/internals/supporting-source-control.md)