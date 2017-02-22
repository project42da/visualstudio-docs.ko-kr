---
title: "레거시 언어 서비스에 탐색 모음에 대 한 지원 | Microsoft Docs"
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
  - "탐색 모음에서 [관리 되는 패키지 프레임 워크] 언어 서비스를 지 원하는"
  - "언어 서비스 [관리 되는 패키지 프레임 워크], 탐색 모음"
ms.assetid: 2d301ee6-4523-4b82-aedb-be43f352978e
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스에 탐색 모음에 대 한 지원
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

편집기 보기의 위쪽에 있는 탐색 모음에서 파일 형식 및 멤버를 표시합니다.  종류는 왼쪽된 드롭 다운에서 나타나며 멤버 드롭다운 오른쪽에 표시 됩니다.  사용자는 형식을 선택 하면 캐럿 종류의 첫 번째 줄에 배치 됩니다.  사용자가 구성원을 선택 하면 멤버 정의에 캐럿 배치 됩니다.  드롭다운 상자 캐럿의 현재 위치를 반영 하도록 업데이트 됩니다.  
  
## 표시 및 탐색 모음 업데이트  
 탐색 모음을 지원 하기 위해 클래스에서 파생 되어야는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 클래스와 구현에 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드.  코드 창에서 기본 언어 서비스를 제공 하면 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스를 인스턴스화하는 <xref:Microsoft.VisualStudio.Package.CodeWindowManager>, 들어는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 코드 창을 나타내는 개체.  <xref:Microsoft.VisualStudio.Package.CodeWindowManager> 개체는 다음 지정 새로운 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 개체입니다.  <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> 메서드를 가져옵니다는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체입니다.  인스턴스를 반환 하는 경우를 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 클래스는 <xref:Microsoft.VisualStudio.Package.CodeWindowManager> 호출을 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 내부를 채우는 방법을 나열 하 고 전달를 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 드롭다운 매니저 도구 모음.  드롭 다운 관리자 도구 모음를 차례로 호출의 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.SetDropdownBar%2A> 메서드를를 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체를 설정 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar> 두 개의 드롭 다운 막대를 포함 하는 개체입니다.  
  
 캐럿을 이동 하는 경우는 <xref:Microsoft.VisualStudio.Package.LanguageService.OnIdle%2A> 메서드 호출에서 <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> 메서드.  기본 <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 클래스 탐색 막대의 상태를 업데이트 합니다.  집합을 전달 하 여 <xref:Microsoft.VisualStudio.Package.DropDownMember> 이 메서드에 개체입니다.  각 개체에 드롭다운 항목을 나타냅니다.  
  
## 탐색 막대의 내용  
 탐색 모음 보통 종류 및 멤버 목록을 포함 합니다.  형식 목록에 사용할 수 있는 모든 유형의 현재 소스 파일에 포함 되어 있습니다.  형식 이름은 전체 네임 스페이스 정보를 포함 합니다.  다음은 두 가지 C\# 코드 예제입니다.  
  
```c#  
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
  
 형식 목록에 표시 됩니다 `TestLanguagePackage.TestLanguageService` 및 `TestLanguagePackage.TestLanguageService.Tokens`.  
  
 구성원 목록 형식 목록에서 선택한 형식의 사용 가능한 멤버를 표시 합니다.  경우 위의 코드 예제를 사용 하 여 `TestLanguagePackage.TestLanguageService` 입니다 선택 된 private 멤버는 멤버 목록이 포함 됩니다 `tokens` 및 `serviceName`.  내부 구조는 `Token` 표시 되지 않습니다.  
  
 구성원 목록에서 구성원 이름 안에 캐럿을 배치할 때 굵게를 구현할 수 있습니다.  멤버에 회색 텍스트를, 캐럿이 현재 배치 되어 있는 범위 내에서 없는 것을 나타내는 표시 될 수도 있습니다.  
  
## 탐색 모음에 대 한 지원 사용  
 탐색 모음에 대 한 지원 기능을 사용 하도록 설정 해야 합니다는 `ShowDropdownBarOption` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 하는 특성 `true`.  이 매개 변수는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> 속성을 설정합니다.  탐색 모음을 지원 하기 위해 구현 해야는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체에 <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> 방법에의 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스.  
  
 구현에는 <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> 메서드를 경우는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> 속성을 설정 `true`, 반환할 수 있습니다는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 개체.  개체를 반환 하지 않는 경우에 탐색 모음 표시 되지 않습니다.  
  
 이 컨트롤에 대 한 편집기 뷰가 열려 있을 때 다시 설정할 수 있으므로 사용자가 탐색 모음을 표시 하는 옵션을 설정할 수 있습니다.  사용자가 닫은 후 다시 열어야 변경 수행 되기 전에 편집기 창입니다.  
  
## 탐색 모음에 대 한 지원을 구현합니다.  
 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 각 목록의 현재 선택 항목을 나타내는 두 개의 값 및 두 목록 \(1 각 드롭 다운에 대 한\) 메서드를 사용 합니다.  목록과 선택 값을 경우에 업데이트할 수는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드가 반환 해야 `true` 목록이 변경 된 것을 나타냅니다.  
  
 구성원 목록 형식 드롭다운에서 선택 영역을 변경할 때 새 형식을 반영 하도록 업데이트 되어야 합니다.  멤버 목록에 표시 되는 내용이 하나 될 수 있습니다.  
  
-   현재 형식에 대 한 구성원 목록이 있습니다.  
  
-   모든 멤버가 사용할 수 있는 원본에서 파일을 있지만 현재 형식에 없는 모든 멤버를 회색 텍스트로 표시 합니다.  사용자가 여전히 빠른 탐색을 위해 사용할 수 있지만, 현재 선택된 된 형식의 부분이 아닌 색을 나타냅니다 흐리게 표시 된 멤버를 선택할 수 있습니다.  
  
 구현 하는 있는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드 일반적으로 다음 단계를 수행 하십시오.  
  
1.  현재 선언 된 소스 파일에 대 한 목록을 가져옵니다.  
  
     다양 한 방법으로 목록을 채울 수 있습니다.  방법 중 하나는 사용자의 버전에 사용자 지정 메서드를 만드는 것은 <xref:Microsoft.VisualStudio.Package.LanguageService> 를 호출 하는 클래스는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드의 모든 선언 목록을 반환 하는 구문 분석 사용자 지정 이유를.  또 다른 방법은 호출 될 수 있습니다는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 에서 직접 메서드를 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드 구문 분석 사용자 지정 이유를.  선언에서 캐시 하는 세 번째 방법을 수 있습니다의 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 마지막 전체 구문 분석 작업에 의해 반환 되는 클래스는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스와 검색은 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드.  
  
2.  채우거 나 형식 목록을 업데이트 합니다.  
  
     형식 목록의 내용을 현재 캐럿 위치에 따라 형식 텍스트 스타일을 변경 하려는 경우 또는 소스가 변경 되었을 때 업데이트 발생할 수 있습니다.  참고가이 위치에 전달 되는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드.  
  
3.  현재 캐럿 위치에 따라 형식 목록에서 선택 하 여 유형을 확인 합니다.  
  
     현재 캐럿 위치를 포함 하는 형식을 찾으려면 1 단계에서 얻은 선언을 검색 하 고 유형 목록 형식 목록에 해당 인덱스를 확인 하려면 해당 형식에 대 한 검색 있습니다.  
  
4.  채우기 또는 선택한 형식에 따라 구성원 목록을 업데이트 합니다.  
  
     구성원 목록에 현재 표시 되어 반영 됩니다 있는  **멤버** 드롭 다운.  구성원 목록의 내용을 원본이 변경 된 경우 또는 선택한 형식의 멤버만 표시 하 여 선택한 유형이 변경 된 경우 업데이트 해야 합니다.  원본 파일의 모든 멤버를 표시 하도록 선택 하면 목록에서 각 구성원의 텍스트 스타일을 현재 선택된 된 형식의 변경 된 경우 업데이트 해야 합니다.  
  
5.  현재 캐럿 위치에 따라 멤버 목록에서 선택할 멤버를 결정 합니다.  
  
     현재 캐럿 위치에 있는 멤버에 대 한 1 단계에서 얻은 선언을 검색 한 다음 멤버 목록 구성원 목록에는 인덱스를 확인 하려면 해당 구성원에 대 한 검색.  
  
6.  반환 `true` 목록 중 하나를 선택 하거나 목록에 변경 내용이 있을 경우.