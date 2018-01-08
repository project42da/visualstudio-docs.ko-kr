---
title: "코어 편집기 안에 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e4612f5779d6177d58cef7f087ef6e11bbe4ebd9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="inside-the-core-editor"></a>코어 편집기 내
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기는 집합을 수정 하 고 텍스트 정보를 쿼리할 수 있는 몇 가지 구성 요소입니다. 코어 편집기 레거시 API를 사용 하 여 사용자 지정, 편집기 어댑터를 통해 라우팅되는 이러한 사용자 지정을 사용 하려면 계속 수 있습니다. 그러나 것, 사용자 지정 항목을 새 편집기 API 조정 합니다.  
  
 다음 영역은 핵심 편집기의 중요 한 점은 다음과 같습니다.  
  
-   텍스트 버퍼  
  
-   텍스트 보기  
  
-   코드 창  
  
-   텍스트 표식  
  
-   텍스트 관리자  
  
-   언어 서비스와의 통합  
  
## <a name="in-this-section"></a>섹션 내용  
 [코어 편집기 레거시 API를 사용 하 여 인스턴스화](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)  
 사용 하는 방법에 대 한 단계별 지침을 제공 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 편집기 코어의 인스턴스를 만들려고 합니다.  
  
 [레거시 API를 사용 하 여 텍스트 버퍼에 액세스](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)  
 핵심 편집기에서 텍스트 버퍼의 역할에 설명, 버퍼에 액세스 하는 데 사용 되 고 텍스트 버퍼 개체에 의해 구현 된 인터페이스의 목록을 제공 하는 관련된 시스템에 설명 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>합니다.  
  
 [레거시 API에서 텍스트 버퍼 이벤트](../extensibility/text-buffer-events-in-the-legacy-api.md)  
 텍스트 버퍼 이벤트 알림에 사용 되는 인터페이스의 목록을 제공 합니다.  
  
 [방법: 레거시 API 사용 하 여 텍스트 버퍼 이벤트 등록](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)  
 텍스트 버퍼 이벤트를 알리기 위해 하는 방법을 설명 합니다.  
  
 [전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 핵심 편집기 구성 요소와 전역 기본 설정 정보를 공유 하는 텍스트 관리자는 방법 및 텍스트 관리자 이벤트에 대 한 알림을 수신 하는 방법을 설명 합니다.  
  
 [레거시 API를 사용 하 여 텍스트 보기에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
 핵심 편집기에서 텍스트 보기의 역할에 설명 하 고 구현한 인터페이스를 나열는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체입니다.  
  
 [레거시 API를 사용 하 여 코드 창을 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)  
 코드 창의 텍스트 보기를 포함 하는 데 사용 됩니다, 코드 창 관리자 장식 코드 창에 제공 하는 방법을 설명 및 새 보기에 대 한 알림을 제공 방법에 대해 설명 합니다.  
  
 [레거시 API를 사용 하 여 보기 설정 변경](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 보기 설정 하는 방법 및 강제 설정을 제거 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [언어 서비스 및 핵심 편집기](../extensibility/language-services-and-the-core-editor.md)  
 제어 코드 장식 하는 언어 서비스의 인스턴스화를 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [연습: 코어 편집기 연결을 만들고 편집기 파일 형식 등록](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)  
 관리 코드에서 코어 편집기를 시작 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [드롭다운 표시줄](../extensibility/drop-down-bar.md)  
 드롭다운 막대로 코드 창에 사용 하 고 드롭다운 표시줄을 구현할 때 사용 되는 인터페이스에 설명 하는 방법을 설명 합니다.  
  
 [텍스트 표식 레거시 API 사용](../extensibility/using-text-markers-with-the-legacy-api.md)  
 텍스트 표식 및 코어 편집기에서 어떻게 사용 되는지를의 개념을 설명 하 고 액세스 하 고 관리할 텍스트 표식이 사용 되는 인터페이스를 나열 합니다.  
  
 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)  
 텍스트 표식을 만드는 방법 및 바로 가기 메뉴에 사용자 지정 명령을 추가 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)  
 사용자 지정 텍스트 마커를 만드는 방법 및 표식 유형을 서비스로 제공 하는 방법에 대 한 단계별 지침을 제공 합니다.