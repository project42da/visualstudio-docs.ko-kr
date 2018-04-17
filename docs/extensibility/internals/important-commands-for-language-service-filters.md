---
title: 언어에 대 한 중요 한 명령을 서비스 필터 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, filters
- language services, commands to support
ms.assetid: 4948c494-3d4d-4f50-b3f9-959e73f90e4d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1e7affdbcad2b935a05420a2817c5d8bda5cd9cf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="important-commands-for-language-service-filters"></a>언어 서비스 필터에 대 한 중요 한 명령
모든 기능 갖춘된 언어 서비스 필터를 만들려면 다음 명령을 처리 하는 것이 좋습니다. 명령 식별자의 전체 목록에 정의 된는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 관리 되지 않는 리소스에 대 한 관리 코드와 Stdidcmd.h 헤더에 대 한 열거형 파일 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 코드입니다. Stdidcmd.h 파일을 찾을 수 *Visual Studio SDK 설치 경로*\VisualStudioIntegration\Common\Inc 합니다.  
  
## <a name="commands-to-handle"></a>핸들에 명령  
  
> [!NOTE]
>  다음 표에서의 모든 명령에 대해 필터링 할 필수는 아닙니다.  
  
|명령|설명|  
|-------------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|클릭할 때 보냅니다. 이 명령은 바로 가기 메뉴를 제공 하기 위해 시간 임을 나타냅니다. 이 명령을 처리 하지 않는 경우 텍스트 편집기 모든 언어 관련 명령이 없는 기본 바로 가기 메뉴를 제공 합니다. 이 메뉴에서 직접 명령을 포함 하려면 명령을 처리 하 고 사용자가 직접 바로 가기 메뉴를 표시 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|일반적으로 다음 사용자가 CTRL + J를 전송 합니다. 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 문 완성 상자를 표시 하도록 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자가 문자를 입력할 때 보냅니다. 이 명령은 트리거 문자를 입력 하 고 문을 제공 하 여 완성, 메서드 팁 및 구문 색 지정 등의 텍스트 표식 중괄호 일치, 시기를 결정 하 고 오류 마커를 모니터링 합니다. 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 문 완성을 위해 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 메서드 팁에 대 한 합니다. 텍스트 표식을 지원 하기 위해이 명령을 입력 하 고 문자 마커를 업데이트 해야 하는지 여부를 확인 하려면를 모니터링 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|다음 사용자가 Enter 키를 전송 합니다. 이 명령을 호출 하 여는 메서드 팁 창을 닫으려면 시기를 결정 하려면 모니터링는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>합니다. 기본적으로 텍스트 보기에는이 명령을 처리합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자가 있는 백스페이스 키를 입력할 때 보냅니다. 호출 하 여 메서드 팁 창 해제할 시기를 결정 하는 모니터는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>합니다. 기본적으로 텍스트 보기에는이 명령을 처리합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|메뉴 또는 바로 가기 키에서 전송 됩니다. 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 팁 창 매개 변수 정보로 업데이트 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|사용자가 변수 위에 마우스를 가져갈 또는 변수에서 커서 위치에 배치를 선택 하는 경우 전송 **요약 정보** 에서 **IntelliSense** 에 **편집** 메뉴. 호출 하 여 변수의 형식을 설명에서 반환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>합니다. 활성 상태 이면 디버깅 팁 변수의 값도 표시 해야 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|일반적으로 다음 사용자가 CTRL + 스페이스바를 전송 합니다. 이 명령은 언어 서비스를 호출 하도록는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID><br /><br /> <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|일반적으로 메뉴에서 보낸 **주석 선택** 또는 **주석 처리 제거 선택** 에서 **고급** 에 **편집** 메뉴. <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 선택한 텍스트를 주석 처리를 사용자에 게 나타냅니다. <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 사용자가 선택한 텍스트를 주석 처리 제거 하려는 나타냅니다. 이 명령은 언어 서비스에만 구현할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)