---
title: "에 항목 추가 된 새 항목 추가 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "새 항목 추가 대화 상자, 항목 추가"
ms.assetid: 2f70863b-425b-4e65-86b4-d6a898e29dc7
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# 에 항목 추가 된 새 항목 추가 대화 상자
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

항목을 추가 하기 위한 프로세스는 **새 항목 추가** 레지스트리 키와 함께 대화 상자를 시작 합니다. AddItemTemplates 섹션의 경로 이름에 사용할 수 있는 어떤 항목에 있는 디렉터리의 다음 레지스트리 항목에 표시 된 것과 같이 포함 된 **새 항목 추가** 대화 상자에 배치 됩니다.  
  
> [!NOTE]
>  바로 다음에 나오는 코드 세그먼트 테이블 레지스트리 항목에 대 한 추가 정보를 포함 합니다.  
  
 이 섹션은 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\14.0Exp\\Projects\] 아래에 있습니다.  
  
 첫 번째 GUID는이 형식의 프로젝트에 대 한 CLSID가 응용 프로그램 두 번째 GUID에는 추가 항목 템플릿에 대 한 등록 된 프로젝트 형식을 나타냅니다.  
  
 {ACEF4EB2\-57CF\-11D2\-96F4\-000000000000} \\{C061DB26\-5833\-11D2\-96F5\-000000000000}\\AddItemTemplates\\TemplateDirs\\ \\1  
  
 @\="\#6"  
  
 "TemplatesDir"\="\< Visual Studio SDK 설치 path\\\\VSIntegration\\\\SomeFolder\\\\SomePackage\\\\SomeProject\\\\SomeProjectItems"  
  
 "SortPriority" dword:00000064 \=  
  
|이름|형식|데이터 \(.rgs 파일\)|설명|  
|--------|--------|---------------------|--------|  
|@ \(기본값\)|REG\_SZ|\#% IDS\_ADDITEM\_TEMPLATES\_ENTRY %|리소스 ID에 대 한 **항목 추가** 템플릿.|  
|Val TemplatesDir|REG\_SZ|%TEMPLATE\_PATH%\\ SomeProjectItems|에 대 한 대화 상자에 표시 되는 프로젝트 항목의 경로 **새 항목 추가** 마법사.|  
|Val SortPriority|REG\_DWORD|100 \([!INCLUDE[vcprx64](../../extensibility/internals/includes/vcprx64_md.md)]\)|에 표시 된 파일의 트리 노드가 정렬 순서를 결정은 **새 항목 추가** 대화 상자입니다.|  
  
> [!NOTE]
>  Visual C\# 및 Visual Basic 프로젝트 형식에 대 한 GUID는 다음과 같습니다:[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]: {FAE04EC0\-301F\-11D3\-BF4B\-00C04F79EFBC}[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]: {F184B08F\-C81C\-45F6\-A57F\-5ABD9991F28F}  
  
 디렉터리 %TEMPLATE\_PATH%\\SomeProjectItems 형식인 TemplateDirs은 노드는 왼쪽에 나열 된 **새 항목 추가** 대화 상자의 트리. 추가 요소 트리의 해당 루트 디렉터리 내에서 하위 디렉터리를 기반으로 합니다. 프로젝트에 추가할 수 있는 파일의 오른쪽 창에 항목이 **새 항목 추가** 대화 상자입니다.  
  
 일반적으로이 폴더는 HTML 서식 파일 또는.cpp 파일을 같은 프로젝트에 대 한 템플릿 파일 및 마법사를 시작 하기 위한 모든.vsz 파일 포함 됩니다. 항목이 표시 되는 방식을 제어 하려면 디렉터리 이름 및 아이콘을 지역화를 위한.vsdir 파일을 포함할 수 있습니다. 지역화 된 문자열은이 트리에서 노드를 새 항목 추가 대화 상자를 나타내는 대화 상자에 표시 되는 캡션을.  
  
 그러나 하나의.vsdir 파일에 있는 모든 필요가 없습니다. 디렉터리에 있는 모든 항목에 대해 하나의.vsdir 파일을 사용할 수 있습니다. 자세한 내용은 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md) 및 [서식 파일 디렉터리 설명 \(합니다. Vsdir\) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)를 참조하세요.  
  
> [!NOTE]
>  서식 파일 디렉터리에 있는.vsdir 파일은 선택적입니다. 프로젝트 구성 요소 디렉터리에 배치 하에서 표시 하려는 경우는 **새 항목 추가** 대화 상자, TemplatesDir 문에 지정 된 템플릿 디렉터리에 해당 파일을 저장할 수 있습니다. 파일의 오른쪽 창에 표시 됩니다는 **새 항목 추가** 해당 프로젝트에 대 한 대화 상자입니다. 그러나 파일 또는 아이콘에 대 한 지역화 된 캡션을 표시 하려는 경우 적어도 하나의.vsdir 파일 템플릿 디렉터리에 포함 해야 합니다.  
  
## 프로젝트 항목 그룹화  
 폴더에 대 한 템플릿 그룹을 포함 하려는 경우는 **새 항목 추가** 대화 상자의 트리 루트 템플릿 디렉터리에 있는 항목으로 아래의 하위 디렉터리에 있어야 합니다. 경우는 **새 항목 추가** 대화 상자가 사용자에 게 표시 됩니다, 또한 하위 폴더를 참조 하 고 프로젝트 요소를 선택할 수는 있습니다.  
  
 코드 세그먼트에서 정렬 우선 순위는 트리 노드의 다른 요소를 기준으로 트리에서이 서식 파일 디렉터리를 만들 위치를 결정 합니다. 에 대 한는 **새 항목 추가** 항목 대화 상자에서 올바른 위치에 표시 되도록 포함 해야 하는 모든 대화 상자, 정렬 우선 순위는 합니다.  
  
 구현할 수도 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> 인터페이스에 표시할 항목을 필터링 하는 **새 항목 추가** 대화 상자입니다. 이 인터페이스를 구현 하 여 설정할 수 있습니다 하나의 서식 파일 디렉터리를 예를 들어 포함 된 디스크에 50 개의 템플릿 및 마법사 파일. 이러한 방법으로 서로 다른 프로젝트 형식과 프로젝트 형식, 다른 프로젝트 형식에 속하는 다른 30 파일 및 프로젝트의 일반 형식에서 사용할 수 있는 모든 파일에 속하는 20 개 파일을 사용할 수 있습니다. 이러한 방식으로 프로젝트에 따라 템플릿을 만든 템플릿 파일의 다른 집합을 표시할 수 있습니다.  
  
 예를 들어 Visual Basic 프로젝트에서 웹 프로젝트와 클라이언트 프로젝트를 할 수 있습니다. Web forms는 클라이언트 프로젝트에 추가할 유용한 항목 않으며 windows forms는 웹 서버 프로젝트에 추가할 유용한 항목은 없습니다. 따라서 두 가지 유형의 프로젝트에 대 한 모든 파일을 포함 한 서식 파일 디렉터리를 만들 수 있습니다. 구현 하 여 다음 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>, 프로젝트 또는 프로젝트의 프로젝트 설정의 종류에 따라 표시 되지 않아야 하는 항목을 숨길 수 있습니다.  
  
## 프로젝트 항목 필터링  
 `IVsFilterAddProjectItemDlg2` 다음과 같은 방법으로 요소 트리 \(왼쪽된 창\) 및 프로젝트 파일 \(오른쪽 창\)에 필터링을 제공 합니다.  
  
-   지역화 된 이름 \(캡션.vsdir 파일에 포함 된 대화 상자에 표시\)으로 제공 하 여 `IVsFilterAddProjectItemDlg`합니다.  
  
-   파일 및 디스크에 폴더의 실제 이름으로 \(지역화 되지 않은\-.vsdir 파일 없음\)에서 제공한 `IVsFilterAddProjectItemDlg`합니다.  
  
-   제공한 범주별 `IVsFilterAddProjectItemDlg2`합니다.  
  
 범주별으로 필터링 하려면 "Web form"와 같은.vsdir 파일의 항목 또는 Visual Basic의 "클라이언트 항목"에 대 한 범주 문자열을 제공 합니다. 그런 다음 대화 상자 코드.vsdir 파일에서 범주 분류를 검색 하 게 전달 합니다. 다음의 구현에 대 한 해당 정보를 전달 `IVsFilterAddProjectItemDlg2` 필터링 하는 **새 항목 추가** 범주별으로 대화 상자입니다. 또한 클라이언트 Win32 응용 프로그램의 경우 또는 웹 페이지에 대 한 항목을 필터링 할 수 있습니다. 식별할 수는 또한 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 항목 클래스 \(MFC\) 또는 액티브 템플릿 라이브러리 \(ATL\) 항목으로 태그가 지정 합니다. 이러한 항목을 식별 하는 경우 시스템은 범주 및 분류에 따라 필터링 할 수 있도록 프로젝트 시스템 자체 분류를 정의할 수 있습니다.  
  
 이 필터 기능을 구현 하는 경우 숨겨야 하는 모든 항목의 테이블에 매핑할 필요가 없습니다. 형식으로 항목을 분류 하 고 분류.vsdir 파일 또는 파일에 삽입 하기만 하면입니다. 그런 다음 인터페이스를 구현 하 여 특정 분류를 포함 하는 항목 중 하나를 숨길 수 있습니다. 이러한 방식으로 항목을 만들 수 있습니다는 **새 항목 추가** 프로젝트 내에서 상태를 기반으로 대화 상자 동적입니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [일반적으로 프로젝트를 확장 하는 데 사용 되는 개체에 대 한 Catid](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [서식 파일 디렉터리 설명 \(합니다. Vsdir\) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)   
 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)