---
title: "항목에 추가 된 새 항목 추가 대화 상자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add New Item dialog box, adding items
ms.assetid: 2f70863b-425b-4e65-86b4-d6a898e29dc7
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f7058d097ab3eb6faeb8acf96b98ae6346887361
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-items-to-the-add-new-item-dialog-boxes"></a>항목에 추가 된 새 항목 추가 대화 상자
항목을 추가 하기 위한 프로세스는 **새 항목 추가** 레지스트리 키를 가진 대화 상자를 시작 합니다. 경로 이름에서 사용할 수 있게 하는 항목에 있는 디렉터리의 AddItemTemplates 섹션에 포함 되어 다음 레지스트리 항목에 나와 있는 것 처럼는 **새 항목 추가** 대화 상자에 배치 됩니다.  
  
> [!NOTE]
>  코드 세그먼트 바로 뒤에 따라오는 테이블 레지스트리 항목에 대 한 추가 정보를 포함 합니다.  
  
 이 섹션 [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0Exp\Projects] 수 있습니다.  
  
 첫 번째 GUID는이 형식의; 프로젝트에 대 한 CLSID 두 번째 GUID에는 추가 항목 템플릿에 대 한 등록 된 프로젝트 형식을 나타냅니다.  
  
 \\{C061DB26-5833-11D2-96F5-000000000000} {ACEF4EB2-57CF-11D2-96F4-000000000000} \AddItemTemplates\TemplateDirs\ \1  
  
 @="#6"  
  
 "TemplatesDir"="\<Visual Studio SDK 설치 경로\\\VSIntegration\\\SomeFolder\\\SomePackage\\\SomeProject\\\SomeProjectItems"  
  
 "SortPriority" dword:00000064 =  
  
|name|형식|데이터 (.rgs 파일)|설명|  
|----------|----------|-----------------------------|-----------------|  
|@ (기본값)|REG_SZ|#% IDS_ADDITEM_TEMPLATES_ENTRY %|에 대 한 리소스 ID **항목 추가** 템플릿.|  
|Val TemplatesDir|REG_SZ|%TEMPLATE_PATH%\ SomeProjectItems|에 대 한 대화 상자에 표시 되는 프로젝트 항목의 경로 **새 항목 추가** 마법사.|  
|Val SortPriority|REG_DWORD|100 ([!INCLUDE[vcprx64](../../extensibility/internals/includes/vcprx64_md.md)])|에 표시 된 파일 트리 노드가 정렬 순서를 결정은 **새 항목 추가** 대화 상자.|  
  
> [!NOTE]
>  Visual C# 및 Visual Basic 프로젝트 형식에 대 한 GUID는 다음과 같습니다:[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]: {FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]: {F184B08F-C81C-45F6-A57F-5ABD9991F28F}  
  
 디렉터리 %TEMPLATE_PATH%\SomeProjectItems 형식인 TemplateDirs의 왼쪽에 노드는 나열 된는 **새 항목 추가** 대화 상자의 트리 합니다. 추가 요소 트리에서 해당 루트 디렉터리 내에서 하위 디렉터리를 기준으로 합니다. 프로젝트에 추가할 수 있는 파일 항목이 오른쪽 창에는 **새 항목 추가** 대화 상자.  
  
 일반적으로이 폴더는 HTML 서식 파일 또는.cpp 파일을 같은 프로젝트에 대 한 템플릿 파일 및 마법사를 시작 하기 위한.vsz 파일 포함 됩니다. 항목이 표시 되는 방식을 제어 하려면 디렉터리 이름 및 아이콘 지역화를 위한.vsdir 파일이 포함할 수 있습니다. 지역화 된 문자열에는이 새 항목 추가 대화 상자 트리이 노드를 나타내는 대화 상자에 표시 되는 캡션을입니다.  
  
 그러나 하나의.vsdir 파일에 모든 항목을 넣이 필요가 없습니다. 디렉터리에 있는 모든 항목에 대해 하나의.vsdir 파일을 포함할 수 있습니다. 자세한 내용은 참조 [마법사 (합니다. Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md) 및 [템플릿 디렉터리 설명 (합니다. Vsdir) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)합니다.  
  
> [!NOTE]
>  서식 파일 디렉터리에 있는.vsdir 파일은 선택적입니다. 에 표시 하는 프로젝트 요소 디렉터리에 저장 합니다. 하 려 할 경우는 **새 항목 추가** 대화 상자, TemplatesDir 문에 지정 된 템플릿 디렉터리에 해당 파일을 넣을 수 있습니다. 파일의 오른쪽 창에 표시 한 다음 됩니다는 **새 항목 추가** 해당 프로젝트에 대 한 대화 상자. 그러나 파일 또는 아이콘에 대 한 지역화 된 캡션이 표시 하려는 경우 템플릿 디렉터리에서 하나 이상의.vsdir 파일을 포함 해야 합니다.  
  
## <a name="grouping-project-items"></a>그룹화 프로젝트 항목  
 템플릿 그룹에 있는 폴더에 포함 하려는 경우는 **새 항목 추가** 대화 상자의 트리 항목으로 템플릿 디렉터리 루트 아래의 하위 디렉터리에 있어야 합니다. 경우는 **새 항목 추가** 대화 상자가 사용자에 게 표시 됩니다는 또한 하위 폴더를 참조 및 프로젝트 요소를 선택할 수 있습니다.  
  
 코드 세그먼트에 정렬 우선 순위는 트리 노드의 다른 요소에 상대적인 트리에서이 서식 파일 디렉터리를 만들 위치를 결정 합니다. 에 대 한는 **새 항목 추가** 대화 상자에서 올바른 위치에 항목을 표시이 포함 해야 하는 모든 대화 상자, 정렬 우선 순위는 합니다.  
  
 구현할 수도 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> 인터페이스에 표시할 항목을 필터링 하는 **새 항목 추가** 대화 상자. 이 인터페이스를 구현 하 여 설정할 수 있습니다 하나 템플릿 디렉터리를 예를 들어 포함 된 디스크에 50 개의 템플릿과 마법사 파일. 이러한 방법으로 한 프로젝트 형식, 다른 프로젝트 형식에 속하는 다른 30 파일 및 일반 형식의 프로젝트에서 사용할 수 있는 모든 파일에 속해 있는 20 개 파일을 사용 하는 다른 프로젝트 형식에 사용할 수 있습니다. 이러한 방식으로 프로젝트에 따라 템플릿을 만든 템플릿 파일의 다른 집합을 표시할 수 있습니다.  
  
 예를 들어 Visual Basic 프로젝트에서 해야할 웹 프로젝트와 클라이언트 프로젝트입니다. Web forms은 클라이언트 프로젝트에 추가할 항목 유용 하지 않으며 windows forms 없습니다 유용에 추가할 항목을 웹 서버 프로젝트. 따라서 두 유형의 프로젝트에 대 한 모든 파일을 포함 한 템플릿 디렉터리를 만들 수 있습니다. 구현 하 여 다음 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>, 프로젝트 또는 프로젝트의 프로젝트 설정의 형식을 기반으로 표시 되지 않아야 하는 항목을 숨길 수 있습니다.  
  
## <a name="filtering-project-items"></a>프로젝트 항목 필터링  
 `IVsFilterAddProjectItemDlg2`다음과 같은 방법으로 트리 (왼쪽된 창) 및 프로젝트 파일 (오른쪽 창)에서 요소를 필터링 하기 위해 제공 합니다.  
  
-   지역화 된 이름 (캡션.vsdir 파일에 포함 된 대화 상자에 표시)으로 제공 하 여 `IVsFilterAddProjectItemDlg`합니다.  
  
-   파일 및 디스크에 폴더의 실제 이름으로 (지역화 되지 않은-.vsdir 파일 없음)에서 제공 `IVsFilterAddProjectItemDlg`합니다.  
  
-   제공한 범주별 `IVsFilterAddProjectItemDlg2`합니다.  
  
 를 범주별으로 필터링 하려면 범주 문자열.vsdir 파일 "Web form" 같은 항목 또는 Visual Basic의 "클라이언트 항목"을 지정 합니다. 대화 상자 코드.vsdir 파일에서 범주 분류를 검색 하 고 사용자에 게 전달 합니다. 구현에 해당 정보에 전달할 수 있습니다 `IVsFilterAddProjectItemDlg2` 필터링 하는 **새 항목 추가** 범주별으로 대화 상자. 또한 클라이언트 Win32 응용 프로그램의 경우 또는 웹 페이지에 대 한 항목을 필터링 할 수 있습니다. 또한 식별할 수 있습니다 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] Microsoft Foundation 클래스 (MFC) 또는 액티브 템플릿 라이브러리 (ATL) 항목으로 항목 태그를 지정 합니다. 이러한 항목을 식별 하는 경우 시스템은 범주 및 분류에 따라 필터링 할 수 있도록 프로젝트 시스템 자체 분류를 정의할 수 있습니다.  
  
 이 필터 기능을 구현 하는 경우 테이블은 숨겨야 하는 모든 항목을 매핑할 필요가 없습니다. 항목 유형으로 분류을.vsdir 파일 또는 파일에서 분류를 배치 하기만 하면 됩니다. 다음 인터페이스를 구현 하 여 특정 분류를 포함 하는 항목 중 하나를 숨길 수 있습니다. 이러한 방식으로 항목을 만들 수 있습니다는 **새 항목 추가** 대화 상자 동적 프로젝트 내에서 상태를 기반 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [일반적으로 프로젝트를 확장 하는 데 사용 되는 개체에 대 한 Catid](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [템플릿 디렉터리 설명 (합니다. Vsdir) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)   
 [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)