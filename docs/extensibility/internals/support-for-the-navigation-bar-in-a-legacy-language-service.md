---
title: "레거시 언어 서비스의 탐색 모음에 대 한 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Navigation bar, supporting in language services [managed package framework]
- language services [managed package framework], Navigation bar
ms.assetid: 2d301ee6-4523-4b82-aedb-be43f352978e
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5e2d7ddfd4904923cbdea415fa5a0d2086cc071f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="support-for-the-navigation-bar-in-a-legacy-language-service"></a>레거시 언어 서비스의 탐색 모음에 대 한 지원
편집기 보기의 위쪽 탐색 모음 파일의 형식 및 멤버를 표시 합니다. 형식은 왼쪽된 드롭다운 목록에서 확인할 및 멤버 드롭 다운 오른쪽에 표시 됩니다. 사용자가 형식을 선택, 캐럿 형식의 첫 번째 줄에 배치 됩니다. 사용자가 구성원을 선택 하면 멤버의 정의에 캐럿 배치 됩니다. 드롭다운 목록 상자는 캐럿의 현재 위치를 반영 하도록 업데이트 됩니다.  
  
## <a name="displaying-and-updating-the-navigation-bar"></a>표시 하 고 업데이트의 탐색 모음  
 탐색 모음을 지원 하려면에서 클래스를 파생 해야 합니다는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 클래스 및 구현 된 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드. 언어 서비스는 코드 창, 기본이 지정 하는 경우 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스를 인스턴스화하는 <xref:Microsoft.VisualStudio.Package.CodeWindowManager>를 포함 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 코드 창을 나타내는 개체입니다. <xref:Microsoft.VisualStudio.Package.CodeWindowManager> 개체에는 새로운 지정 다음 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 개체입니다. <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체입니다. 인스턴스를 반환 하는 경우 프로그램 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 클래스는 <xref:Microsoft.VisualStudio.Package.CodeWindowManager> 호출 프로그램 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드 내부를 채우는를 나열 하 고 전달 프로그램 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 막대 관리자 드롭 다운 합니다. 드롭 다운 표시줄 관리자를 호출 하는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.SetDropdownBar%2A> 메서드를 프로그램 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 설정 하기 위해 개체는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar> 두 개의 드롭다운 막대를 보유 하는 개체입니다.  
  
 캐럿 움직이면는 <xref:Microsoft.VisualStudio.Package.LanguageService.OnIdle%2A> 메서드 호출에서 <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> 메서드. 기본 <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 에서 메서드 프로그램 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 탐색 모음의 상태를 업데이트 하는 클래스입니다. 집합을 전달 하면 <xref:Microsoft.VisualStudio.Package.DropDownMember> 이 메서드에 개체입니다. 각 개체 드롭다운 목록에서 항목을 나타냅니다.  
  
## <a name="the-contents-of-the-navigation-bar"></a>탐색 모음 내용  
 탐색 모음 유형 목록 및 멤버 목록은 일반적으로 포함 되어 있습니다. 형식 목록에는 현재 소스 파일에서 사용할 수 있는 모든 형식을 포함 됩니다. 전체 네임 스페이스 정보를 포함 하는 형식 이름입니다. 다음은 두 가지 유형이 C# 코드 예제입니다.  
  
```csharp  
namespace TestLanguagePackage  
{  
    public class TestLanguageService  
    {  
        internal struct Token  
        {  
            int tokenID;  
        }  
        private Tokens[] tokens;  
        private string serviceName;  
    }  
}  
```  
  
 형식 목록에 표시 됩니다 `TestLanguagePackage.TestLanguageService` 및 `TestLanguagePackage.TestLanguageService.Tokens`합니다.  
  
 멤버 목록 형식 목록에서 선택 된 형식의 사용 가능한 구성원을 표시 합니다. 경우에 위의 코드 예제를 사용 하 여 `TestLanguagePackage.TestLanguageService` 을 선택 하는 형식 멤버 목록에는 private 멤버 포함 `tokens` 및 `serviceName`합니다. 내부 구조 `Token` 표시 되지 않습니다.  
  
 멤버 목록에서 그 안에 캐럿 배치는 멤버의 이름을 굵게 표시 된 확인을 구현할 수 있습니다. 멤버 수 또한에 회색으로 표시 텍스트를 나타내는 표시 캐럿 현재 배치 되어 범위에 포함 되지 않는.  
  
## <a name="enabling-support-for-the-navigation-bar"></a>탐색 모음에 대 한 지원을 사용 하도록 설정  
 에 있는 탐색 모음에 대 한 지원을 사용 하려면 설정 해야 합니다는 `ShowDropdownBarOption` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 특성을 `true`합니다. 이 매개 변수는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> 속성을 설정합니다. 탐색 모음을 지원 하려면 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체에 <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스.  
  
 구현에서는 <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> 메서드를 하는 경우는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> 속성이로 설정 되어 `true`를 반환할 수 있습니다는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체입니다. 개체를 반환 하지 않는 경우 탐색 모음 표시 되지 않습니다.  
  
 이 컨트롤 편집기 보기 열려 있는 동안 다시 설정할 수 있도록 사용자가 탐색 모음을 표시 하는 옵션을 설정할 수 있습니다. 사용자를 닫고 변경 내용을 수행 되기 전에 편집기 창을 다시 열려면 해야 합니다.  
  
## <a name="implementing-support-for-the-navigation-bar"></a>탐색 모음에 대 한 지원 구현  
 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드는 두 개의 목록 (각 드롭다운에 대해 각각 하나씩) 및 각 목록에서 현재 선택 영역을 나타내는 두 개의 값을 사용 합니다. 목록과 선택 값을 업데이트할 수는 쿼리에서 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드는 반환 해야 `true` 를 나타내는 목록 변경 되었습니다.  
  
 형식 드롭다운 목록에서에서 선택이 변경으로 멤버 목록 새 유형을 반영 하도록 업데이트 되어야 합니다. 멤버 목록에 표시 되는 내용을 다음 중 하나일 수 있습니다.  
  
-   현재 형식에 대 한 멤버의 목록입니다.  
  
-   원본에 사용할 수 있는 모든 멤버 파일, 하지만 현재 형식에 없는 모든 멤버와 회색 텍스트로 표시 합니다. 빠른 탐색을 위해 사용할 수 있지만 색은 없음을 나타냅니다 현재 선택 된 형식에 포함 되므로 회색 멤버를 여전히 선택할 수 있습니다.  
  
 구현에서 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드는 일반적으로 다음 단계를 수행 합니다.  
  
1.  소스 파일에 대 한 현재 선언의 목록을 가져옵니다.  
  
     방법으로는 목록을 채울 수가 있습니다. 버전에는 사용자 지정 메서드를 만드는 한 가지 방법은 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스를 호출 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 모든 선언의 목록을 반환 하는 사용자 지정 구문 분석 이유와 메서드. 또 다른 방법은를 호출할 수 있습니다는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 에서 직접 메서드는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드 구문 분석 사용자 지정 이유를 사용 합니다. 세 번째 차후에서 선언을 캐시할 수도 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 의 마지막 전체 구문 분석 작업에서 반환 된 클래스는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 하 고 검색 하는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드.  
  
2.  채우거 나 형식의 목록을 업데이트 합니다.  
  
     형식 목록의 콘텐츠는 소스가 변경 된 경우 또는 현재 캐럿 위치에 따라 형식의 텍스트 스타일을 변경 하려면 선택한 경우 업데이트할 수 있습니다. 이 위치에 전달 되는 참고는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드.  
  
3.  현재 캐럿 위치에 따라 형식 목록에서 선택 하려면 유형을 결정 합니다.  
  
     현재 캐럿 위치를 포함 하는 형식을 찾기 위해 1 단계에서 가져온 선언을 검색 하 고 형식 목록에 해당 항목이 있는 인덱스를 확인 하려면 해당 형식에 대 한 형식 목록을 검색 합니다.  
  
4.  채우거 나 선택한 형식을 기반으로 하는 멤버의 목록을 업데이트 합니다.  
  
     멤버 목록에 현재 표시 되는 내용에 반영 된 **멤버** 드롭 다운 합니다. 멤버 목록의 내용을 소스 변경 된 경우 또는 선택한 형식의 멤버만 표시 하는 선택한 형식의 변경 된 경우 업데이트 해야 합니다. 를 소스 파일의 모든 멤버를 표시 하도록 선택 목록에서 각 구성원의 텍스트 스타일을 업데이트 하 여 현재 선택 된 형식이 변경 해야 합니다.  
  
5.  현재 캐럿 위치에 따라 멤버 목록에서 선택 하는 멤버를 결정 합니다.  
  
     현재 캐럿 위치를 포함 하는 멤버에 대 한 가져온 선언 1 단계에서 검색 한 다음 멤버 목록에 해당 항목이 있는 인덱스를 확인 하려면 해당 멤버에 대 한 멤버 목록을 검색 합니다.  
  
6.  반환 `true` 는 목록이 나 목록에서 선택 항목에 변경 내용을 적용 된 경우.