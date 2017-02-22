---
title: "코어 편집기 내 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-코어 편집기"
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
caps.latest.revision: 21
caps.handback.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
---
# 코어 편집기 내
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기를 수정 하 고 텍스트 정보를 쿼리할 수 있는 여러 구성 요소의 집합입니다.  기존 API를 사용 하 여 핵심 편집기를 사용자 지정한 경우 편집기 어댑터를 통해 라우팅됩니다.이 지정을 사용 하 여 계속 합니다.  그러나, 사용자 지정 내용이 새 편집기 API에 적응 한다는 것입니다.  
  
 다음 영역의 핵심 편집기의 몇 가지 중요 한 측면입니다.  
  
-   텍스트 버퍼  
  
-   텍스트 보기  
  
-   코드 창  
  
-   텍스트 마커  
  
-   텍스트 관리자  
  
-   언어 서비스와의 통합  
  
## 단원 내용  
 [코어 편집기 레거시 API를 사용 하 여 인스턴스화](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)  
 사용 하는 방법에 대 한 단계별 지침을 제공 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 편집기 핵심의 인스턴스를 만들 수 있습니다.  
  
 [레거시 API를 사용 하 여 텍스트 버퍼에 액세스](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)  
 코어 편집기에서 텍스트 버퍼의 역할을 설명 하 고 버퍼에 액세스 하는 데 사용 됩니다 및 텍스트 버퍼 개체에 의해 구현 된 인터페이스의 목록을 제공 하는 관련된 시스템 설명 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 [레거시 API에서 텍스트 버퍼 이벤트](../extensibility/text-buffer-events-in-the-legacy-api.md)  
 텍스트 버퍼 이벤트 알림을 사용 하는 인터페이스를 제공 합니다.  
  
 [방법: 레거시 API와 함께 텍스트 버퍼 이벤트에 등록](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)  
 텍스트 버퍼 이벤트를 조언 하는 방법을 설명 합니다.  
  
 [텍스트 관리자를 사용 하 여 전역 설정 모니터링](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 텍스트 관리자를 사용 하 여 코어 편집기 구성 요소를 전역 기본 설정 정보를 공유 하는 방법 및 텍스트 관리자 이벤트 알림을 수신 하는 방법에 설명 합니다.  
  
 [텍스트 보기에 액세스 하는 레거시 API를 사용 하 여](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
 코어 편집기의 텍스트 보기의 역할에 설명 하 고에 의해 구현 된 인터페이스를 나열은 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체입니다.  
  
 [레거시 API를 사용 하 여 코드를 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)  
 어떻게 코드 창 텍스트 뷰를 묶는 데 사용 됩니다, 코드 창 관리자를 사용 하 여 장식의 코드 창 제공 합니다 하는 방법에 대해 설명 합니다 및 새 보기에 대 한 알림을 제공 하는 방법에 설명 합니다.  
  
 [레거시 API를 사용 하 여 보기 설정 변경](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 보기 설정 하 고 강제 설정을 제거 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [언어 서비스 및 코어 편집기](../extensibility/language-services-and-the-core-editor.md)  
 언어 서비스에 코드 장식 컨트롤의 인스턴스를 설명합니다.  
  
## 관련 단원  
 [연습: 코어 편집기 만들기 및 등록 하는 편집기 파일 형식](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)  
 코어 편집기에서 관리 되는 코드를 시작 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [드롭다운 표시줄](../extensibility/drop-down-bar.md)  
 드롭다운 표시줄로 코드 창에 사용 됩니다 및 드롭 다운 막대를 구현할 때 사용 되는 인터페이스에 설명 하는 방법 설명 합니다.  
  
 [레거시 API와 함께 텍스트 마커를 사용 하 여](../extensibility/using-text-markers-with-the-legacy-api.md)  
 텍스트 마커 및 코어 편집기에서 사용 되는 개념에 설명 하 고 액세스 하 고 텍스트 마커를 관리 하는 데 사용 되는 인터페이스 목록을 표시 합니다.  
  
 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)  
 텍스트 마커를 만드는 방법 및 사용자 지정 명령을 바로 가기 메뉴에 추가 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)  
 사용자 정의 텍스트 마커를 만드는 방법 및 표식 종류의 서비스를 제공 하는 방법에 대 한 단계별 지침을 제공 합니다.