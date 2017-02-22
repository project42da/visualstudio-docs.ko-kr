---
title: "언어 서비스 필터에 대 한 중요 한 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스, 필터"
  - "언어 서비스를 지원 하기 위해 명령"
ms.assetid: 4948c494-3d4d-4f50-b3f9-959e73f90e4d
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 언어 서비스 필터에 대 한 중요 한 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

완전 한 기능의 언어 서비스 필터를 만들려면 다음 명령을 처리 하는 것이 좋습니다.  명령 식별자의 전체 목록에 정의 되어 있는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 열거에 관리 되는 코드 및 Stdidcmd.h 헤더 파일을 않는 대 한 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 코드입니다.  Stdidcmd.h 파일에서 찾을 수 있습니다  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration\\Common\\Inc.  
  
## 핸들을 명령  
  
> [!NOTE]
>  다음 표에 각 명령에 대 한 필터링 하는 데 필수입니다.  
  
|명령|설명|  
|--------|--------|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자를 마우스 오른쪽 단추로 클릭할 때 보냅니다.  이 명령을 바로 가기 메뉴를 제공 하는 시간입니다.  이 명령을 처리 하지 않는 경우 기본 바로 가기 메뉴는 특정 언어 관련 명령 없이 텍스트 편집기를 제공 합니다.  이 메뉴에서 직접 명령을 포함 명령을 처리 한 직접 바로 가기 메뉴를 표시 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자가 CTRL \+ J를 입력할 때 일반적으로 전송 합니다.  호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 방법에의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 문 완성 상자를 표시 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자가 문자를 입력할 때 전송 합니다.  오류 표식 및 문을 제공 하십시오 완성, 방법 팁 및 구문 색 등 텍스트 마커 일치 중괄호 트리거 문자를 입력 하면이 명령은 모니터링 합니다.  호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 방법에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 문 완성을 위해 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 방법 설명 하는 팁.  텍스트 마커를 지원 하려면 입력 한 문자에 마커를 업데이트 해야 하는지 여부를 확인 하려면이 명령을 모니터링 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자가 Enter 키를 입력할 때 전송 합니다.  메서드 설명 창이 호출 하 여 해제 해야 하는 경우이 명령은 모니터링은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> 방법에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>.  기본적으로이 명령은 텍스트 뷰를 처리합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|백스페이스 키를 사용자가 입력할 때 보냅니다.  메서드 설명 창이 호출 하 여 해제 해야 하는 경우 확인 하려면 모니터의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>.  기본적으로이 명령은 텍스트 뷰를 처리합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|메뉴 또는 바로 가기 키를 전달 합니다.  호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> 방법에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 설명 창이 함께 매개 변수 정보를 업데이트 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자 변수 위로 이동 하거나 커서 변수에서 위치를 선택 하면 보낸  **요약 정보** 에서  **IntelliSense** 에 있는  **편집** 메뉴입니다.  호출 하 여 변수의 형식 설명에 반환의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> 방법에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.  디버깅 활성화 되어 있으면 끝 변수 값도 표시 됩니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|CTRL \+ 스페이스바를 누르면 사용자가 입력 하는 경우 일반적으로 전송 합니다.  이 언어 서비스를 호출할 수 있게는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID><br /><br /> <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|일반적으로 메뉴의 보낸  **주석을 선택** 또는  **선택 영역의 주석 처리 제거** 에서  **고급** 에  **편집** 메뉴.  <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>사용자가 선택한 텍스트를 주석으로 처리 하려고 한다는 것을 나타냅니다.  <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>사용자가 선택한 텍스트의 주석 처리를 제거 하려고 한다는 것을 나타냅니다.  언어 서비스에만 이러한 명령은 구현할 수 있습니다.|  
  
## 참고 항목  
 [언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)