---
title: "편집기에서 레거시 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4b437dad35850a20696702b84d8ea98ead8a1e9e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-interfaces-in-the-editor"></a>편집기에서 레거시 인터페이스
Visual Studio 편집기에서 레거시 인터페이스에 액세스할 수 있습니다. 라고 하는 어댑터를 포함 하는 Visual Studio SDK *shim*, 이러한 인터페이스를 새 편집기와 상호 작용할 수 있도록 합니다. 그럼에도 불구 하 고 새 편집기 API를 사용 하 여 레거시 코드를 업데이트 하는 것이 좋습니다. 사용자 코드에서 더 잘 수행 하 고 (WPF (Windows Presentation Foundation) 및는 프레임 워크 MEF (Managed Extensibility)와 같은 새로운 기술을 사용할 수 있습니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[레거시 코드 편집기를 적용합니다.](../extensibility/adapting-legacy-code-to-the-editor.md)|새 편집기 코드를 조정 하는 방법에 설명 합니다.|  
|[편집기 어댑터로 새롭거나 변경 된 동작](../extensibility/new-or-changed-behavior-with-editor-adapters.md)|편집기의 이전 버전에서 편집기 어댑터의 동작 차이점에 대해 설명 합니다.|  
|[코어 편집기 내](../extensibility/inside-the-core-editor.md)|편집기의 이전 버전의 다양 한 구성 요소에 설명합니다.|  
|[코어 편집기 레거시 API를 사용 하 여 인스턴스화](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)|코어 편집기를 인스턴스화하는 레거시 API를 사용 하는 방법에 설명 합니다.|  
|[편집기 팩터리](../extensibility/editor-factories.md)|레거시 API와 편집기 팩터리를 사용 하는 방법에 설명 합니다.|  
|[방법: 편집기 파일 형식 등록](../extensibility/how-to-register-editor-file-types.md)|편집기에는 파일 이름 확장명을 연결 하는 방법에 설명 합니다.|  
|[연습: 코어 편집기 연결을 만들고 편집기 파일 형식 등록](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)|핵심 편집기를 만들고 파일 이름 확장명에 연결 하는 방법에 설명 합니다.|  
|[방법: 편집기에 대 한 컨텍스트를 제공 합니다.](../extensibility/how-to-provide-context-for-editors.md)|편집기에 대 한 컨텍스트를 제공 하는 방법에 설명 합니다.|  
|[언어 서비스 및 핵심 편집기](../extensibility/language-services-and-the-core-editor.md)|언어 서비스와 편집기 간의 상호 작용에 설명합니다.|  
|[레거시 API를 사용 하 여 텍스트 버퍼에 액세스](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)|레거시 API를 사용 하 여 텍스트 버퍼에 액세스 하는 방법에 설명 합니다.|  
|[레거시 API를 사용 하 여 텍스트 보기에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)|레거시 API를 사용 하 여 텍스트 보기에 액세스 하는 방법에 설명 합니다.|  
|[레거시 API를 사용 하 여 코드 창을 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)|레거시 API를 사용 하 여 코드 창을 사용자 지정 하는 방법에 설명 합니다.|  
|[레거시 API를 사용 하 여 텍스트 계층에 액세스](../extensibility/accessing-text-layers-by-using-the-legacy-api.md)|레거시 API를 사용 하 여 텍스트의 다른 계층에 액세스 하는 방법에 설명 합니다.|  
|[텍스트 표식 레거시 API 사용](../extensibility/using-text-markers-with-the-legacy-api.md)|텍스트 표식 레거시 API를 사용 하 여 추가 하는 방법에 설명 합니다.|  
|[레거시 API를 사용 하 여 편집기 컨트롤 및 메뉴를 사용자 지정](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)|레거시 API를 사용 하 여 편집기 컨트롤을 사용자 지정 하는 방법에 설명 합니다.|  
|[실행 취소 관리와 레거시 API를 사용 하 여 다시 실행](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md)|실행 취소 관리와 레거시 API를 사용 하 여 다시 실행 하는 방법에 설명 합니다.|  
|[방법: 찾기 구현 및 메커니즘을 바꾸기](../extensibility/how-to-implement-the-find-and-replace-mechanism.md)|찾기를 관리 하 고 기존 API를 사용 하 여 대체 하는 방법에 설명 합니다.|  
|[방법: 파일 변경 알림 표시 안 함](../extensibility/how-to-suppress-file-change-notifications.md)|레거시 API를 사용 하 여 파일 변경 알림을 표시 하는 방법에 설명 합니다.|  
|[사용자 지정 편집기 및 디자이너 만들기](../extensibility/creating-custom-editors-and-designers.md)|사용자 지정 편집기 및 디자이너를 만드는 방법에 설명 합니다.|  
|[레거시 언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)|사용자 지정 기능을 제공 하는 기능에 대 한 문서에 대 한 링크를 제공는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 언어 서비스에 대 한 지원을 추가 하 여 코어 편집기입니다.|  
|[글꼴 및 색을 사용 하 여](../extensibility/using-fonts-and-colors.md)|레거시 인터페이스 글꼴 및 색을 사용 하는 방법에 설명 합니다.|